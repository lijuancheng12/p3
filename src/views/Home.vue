<template>
  <div id="home">
    <h2 class="title">Sverige Radio P3:s tablå</h2>
    <ProgramTable :programs='apiData.schedule'/>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Home',
  components: {
    ProgramTable:() => import('@/components/ProgramTable.vue')
  },
  data:() =>({ 
    apiData: {}

  }),
  async created() {
    const res = await axios.get("https://api.sr.se/api/v2/scheduledepisodes?channelid=164&format=json");
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
}
</style>
