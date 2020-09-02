<template>
  <div id="home">
    <Header />
    <h1 id="topp">Lijuan Cheng</h1>
    <h5>Front end developer</h5>
    <Skill />
    <a href="#portfolio" id="to-portfolio">
      <DownArrow />
    </a>
    <Portfolio />
    <About />
    
    <Contact />
  </div>
</template>

<script>
import Contact from "../components/Contact.vue";
import About from "../components/About.vue";
import Header from "../components/Header.vue";
import Portfolio from "../components/Portfolio.vue";
import Skill from "../components/Skill.vue";
import DownArrow from "../components/DownArrow.vue";
export default {
  name: "Home",
  components: {
    About,
    Contact,
    Header,
    Portfolio,
    Skill,
    DownArrow
  }
};
</script>
<style  lang ="scss" scoped>
@import "../assets/scss/main.scss";

#home {
  width:100vw;
  /*height: 100vh;*/
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  h1 {
    margin-top: 200px;
    text-align: center;
    letter-spacing: 2rem;
    font-size: 5rem;
    font-family: "Fredoka One", cursive;
    color: $pink;
  }
  h5 {
    color: white;
    font-size: 1rem;
    letter-spacing: 0.5rem;
  }
  #to-portfolio {
margin-top: 300px;  }
}
@media screen and (max-width: 500px) {
    #home{
        width: 100vw;
        h1{
          margin-top: 200px;
          font-size: 2rem;
        }
        h5{
          margin-top:10px;
        }
    }
}
</style>
