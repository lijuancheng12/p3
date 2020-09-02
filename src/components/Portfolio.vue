<template>
 <div id="port">
  <section id="portfolio">
    <div class="wrapper">
      <Picture v-for="picture in pictures" :key="picture.title" :picture="picture" />
    </div>
    
  </section>
  <a href="#about" id="to-about">
      <DownArrow />
    </a>
 </div>
</template>

<script>
import bild1 from "../assets/bild1.png";
import bild4 from "../assets/bild4.png";
import bild3 from "../assets/bild3.png";
import bild5 from "../assets/bild5.png";
import bild2 from "../assets/bild2.png";
import bild6 from "../assets/bild6.png";
import Picture from "./Picture.vue";
import DownArrow from "./DownArrow.vue";
export default {
  components: {
    Picture,
    DownArrow,
  },
  data() {
    return {
      pictures: [
        {
          title: "Events booking page",
          url: "https://github.com/jenseneducation-lijuan-cheng/events-vuex",
          picture: bild1,
          description:
            "A school project to make a page for booking and managing events"
        },
        {
          title: "Library",
          url: "",
          picture: bild4,
          description:
            "A school project to make a page with information about some children's books"
        },
        {
          title: "Shoppen",
          url: "https://github.com/jenseneducation-lijuan-cheng/webbproject2",
          picture: bild3,
          description: "A school project to make a web shop in node.js"
        },
        {
          title: "E-wallet",
          url:
            "https://github.com/jenseneducation-lijuan-cheng/project-e-wallet",
          picture: bild5,
          description:
            "A school project to make an E-wallet application using Vue"
        },
        {
          title: "Coffee Bean",
          url: "https://github.com/jenseneducation-lijuan-cheng/vuexproject",
          picture: bild2,
          description:
            "A school project to make a page for a web shop selling coffee"
        },
        {
          title: "Pendlaren",
          url: "https://github.com/jenseneducation-lijuan-cheng/PWA-pendlaren",
          picture: bild6,
          description:
            "A PWA to find public transportation departures near your location"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";



section {
  position:relative;
  padding-top: 100px;
  margin: 500px auto 100px;
  width: 1200px;
  

  .wrapper {
    display: flex;
    flex-wrap: wrap;
  }
 // #to-about {
 // margin-top:50px;
//}
}
@media screen and (max-width: 500px) {
    #port{
      section {
        width: 100vw;
      }
       
        

    }
}

</style>