<template>
  <div>
      <div>Visar:</div>
      <div v-for="program in programs" :key="program.program.id">
          <div>Tiden:{{}}</div>
          <div>Icon:{{}}</div>
          <div>Title:{{program.title}}
              <div class="show-more-info">Visa mer+<span>beskrivning:{{}}</span></div>
          </div>
      </div>
    
  </div>
</template>

<script>
export default {
  name: 'ProgramTable',
 props:['programs']
};
</script>
<style lang="scss" scoped>
@import '../assets/scss/main.scss';
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap');

#home {
  background: #ffffff;
  height: 100vh;
  padding: 20px;
  .title {
    color: #1c1b1b;
    font-family: Poppins;
    font-size: 30px;
  }
  .show-more-info{
      cursor: pointer;
  }
}
</style>
