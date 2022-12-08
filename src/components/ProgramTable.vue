<template>
  <div>
    <div
      v-for="(program, idx) in programs"
      :key="idx"
      class="program-container table-border"
    >
      <div class="program-text">{{ getDate(program.starttimeutc) }}</div>
      <img :src="program.imageurl" class="program-image" />
      <div>
        <div class="program-text">
          {{ program.title }}
        </div>
        <div class="show-more-info show-info" @click="toggleShow(idx)">
          Visa mer +
        </div>
        <p class="show-more-info" v-if="shouldShow(idx)">
          {{ program.description }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProgramTable',
  props: ['programs'],
  data: () => ({
    showDescription: []
  }),
  methods: {
    shouldShow(id) {
      if (this.showDescription.indexOf(id) != -1) {
        return true;
      }
    },
    toggleShow(id) {
      if (this.shouldShow(id)) {
        this.showDescription = this.showDescription.filter((x) => x != id);
      } else {
        this.showDescription.push(id);
      }
    },
    getDate(str) {
      const start = str.indexOf('(');
      const end = str.indexOf(')');
      // find the number in ther date string then parse it. 
      const time = new Date(parseInt(str.substring(start + 1, end)));
      const hours = time.getHours();
      const minutes = time.getMinutes();
      return (
        (hours < 10 ? '0' : '') +
        hours +
        ':' +
        (minutes < 10 ? '0' : '') +
        minutes
      );
    }
  }
};
</script>
<style lang="scss" scoped>
@import '../assets/scss/main.scss';
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap');
.show-date {
  margin: 20px 0px 50px 0px;
  font-family: Poppins;
}
.program-container {
  display: flex;
  flex-direction: row;
  padding: 12px 0px 12px 45px;
  .program-text {
    font-size: 16px;
    font-family: Poppins;
    color: #1c1b1b;
  }
  .show-more-info {
    cursor: pointer;
    font-family: sans-serif;
    font-size: 14px;
  }
  .show-info {
    color: $pink;
    border: none;
    width: 100px;
  }
  .program-image {
    width: 50px;
    height: 50px;
    border-radius: 8px;
    margin: 0px 10px;
  }
}
.table-border {
  border-bottom: 1px solid #cccccc;
  margin: 1px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
</style>
