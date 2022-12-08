<template>
  <div id="home">
    <h2 class="title">Sverige Radio P3:s tablå</h2>
    <div class="show-date-programs">
      <div class="show-date">Visar:</div>
      <button
        v-for="(day, idx) in week"
        :key="idx"
        class="date-buttons"
        @click="selectedIdx = idx"
      >
        {{ buttonTitle(idx) }}
      </button>
    </div>

    <ProgramTable :programs="apiData.schedule" />
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Home',
  components: {
    ProgramTable: () => import('@/components/ProgramTable.vue')
  },
  data: () => ({
    apiData: {},
    selectedIdx: 0
  }),
  computed: {
    week() {
      let days = [];
      const today = new Date();
      days.push(today);
      for (let i = 1; i < 7; i++) {
        let d = new Date();
        d.setDate(today.getDate() + i);
        days.push(d);
      }
      return days;
    }
  },
  methods: {
    buttonTitle(idx) {
      if (idx === 0) {
        return 'Idag';
      } else if (idx == 1) {
        return 'Imorgon';
      }
      const day = this.week[idx];
      return `${day.getFullYear()}-${day.getMonth() + 1}-${day.getDate()}`;
    }
  },
  watch: {
    async selectedIdx(idx) {
      const day = this.week[idx];
      const date = `${day.getFullYear()}-${day.getMonth() +
        1}-${day.getDate()}`;
      const res = await axios.get(
        'https://api.sr.se/api/v2/scheduledepisodes?channelid=164&format=json&size=100&date=' +
          date
      );
      this.apiData = res.data;
    }
  },
  async created() {
    const res = await axios.get(
      'https://api.sr.se/api/v2/scheduledepisodes?channelid=164&format=json&size=100'
    );
    this.apiData = res.data;
  }
};
</script>
<style lang="scss" scoped>
@import '../assets/scss/main.scss';
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap');

#home {
  background: #ffffff;
  padding: 20px;
  .title {
    color: #1c1b1b;
    font-family: Poppins;
    font-size: 30px;
  }
  .show-date-programs {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin: 20px 0px 50px 0px;
    font-family: Poppins;
    .date-buttons {
      color: #1c1b1b;
      border:none;
      border-radius: 15px;
      margin: 15px;
      padding: 5px;
      font-size: 14px;
      font-family: sans-serif;
      cursor: pointer; 
    }
     .date-buttons:hover {
        background: $green;
        color:#ffffff;
      }
  }
}
</style>
