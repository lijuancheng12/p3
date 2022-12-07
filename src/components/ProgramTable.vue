<template>
  <div>
      <div>Visar:</div>
      <div v-for="(program, idx) in programs" :key="idx" class="program-container">
          <div class="program-text">{{getDate(program.starttimeutc)}}</div>
          <img :src="program.imageurl"  class="program-image"/>
          <div class="program-text">{{program.title}}
              <div class="show-more-info show-info" @click="toggleShow(idx)">Visa mer +</div>
              <p class="show-more-info" v-if="shouldShow(idx)">beskrivning:{{program.description}}</p>
          </div>
      </div>
    
  </div>
</template>

<script>
export default {
  name: 'ProgramTable',
 props:['programs'],
  data:() =>({ 
   showDescription:[],


  }),
  methods:{
    shouldShow(id){
      if (this.showDescription.indexOf(id) != -1){
         return true
      }
    },
    toggleShow(id) {
    
      if (this.shouldShow(id)) {
        this.showDescription = this.showDescription.filter(x => x != id);
      } else {
        this.showDescription.push(id);
      }
    },
    getDate(str) {
      const start = str.indexOf("(");
      const end = str.indexOf(")");
      return new Date(parseInt(str.substring(start + 1, end))).toISOString().split("T")[0]
    }
  }
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
  .program-container{
    display: flex;
    flex-direction: row;
  .program-text{
      font-size: 16px;
      font-family:Poppins;
      color: #1c1b1b;
    }
  .show-more-info{
      cursor: pointer;
      font-family: sans-serif;
  }
  .show-info{
    
     color:$pink;
     width: 100px;
     text-align: center;
  } 
  .program-image{
    width: 50px;
    height: 50px;
    border-radius: 8px;
    margin: 0px 10px;
  }
  }
}
</style>
