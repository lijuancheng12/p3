<template>
  <div id="container">
    <section id="about">
      <div class="jagWrapper">
        <div class="jag">
          <img src="@/assets/jag.jpg" class="me" />
        </div>
      </div>
      <div class="text">
        <div class="first">
          <h3>BIO</h3>
          <p>
            Jag kommer från Kina och jag har bott nästan 5 år i Sverige.
            <br />Jag är utbildad musiklärare från början.
            <br />Nu studerar jag frontend-utveckling på Jensen yrkeshögskola och letar LiA-plats.
          </p>
        </div>
        <div class="part2">
          <div class="second">
            <h3>Intressen</h3>
            <p>
              Jag är intreserad av många saker.
              <br />Mina största intressen är inredning, mat, resor och musik.
              <br />Jag tycker att det är jätteroligt att plocka svamp, speciellt kantareller!
              <br />Dessutom tycker jag om att titta på thrillers.
            </p>
          </div>
          <div class="tree">
            <h3>Erfarenhet</h3>
            <p>
              Innan jag blev utvecklare har jag gjort flera olika saker.
              Jag har jobbat inom serviceyrken som affär och café.
              <br />
              <br />Jag är från början utbildad i musik och har jobbat som musiklärare på gymnasiet och som förskollärare i Kina.
            </p>
          </div>
        </div>
      </div>
    </section>
    <a href="#contact">
      <DownArrow />
    </a>
  </div>
</template>

<script>
import DownArrow from "./DownArrow.vue";
export default {
  components: {
    DownArrow
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";
#container {
  margin: 500px;
}
#about {
  width: 1200px;
  margin: auto;
  height: 90vh;
  display: flex;
  flex-direction: row;
  //justify-content: center;
  //align-items: center;
  .jagWrapper {
    flex: 1;
    align-self: center;

    .jag {
      width: 200px;
      height: 200px;
      overflow: hidden;
      border-radius: 60%;

      .me {
        width: 200px;
      }
    }
  }
  .text {
    color: rgb(122, 115, 115);
    font-size: 1rem;
    letter-spacing: 2px;
    flex: 2;
    display: flex;
    flex-direction: column;
    align-self: center;
    .first {
      margin-bottom: 50px;
    }
    .part2 {
      display: flex;
      flex-direction: row;

      .second {
        padding-right: 20px;
        line-height: 30px;
      }

      .tree {
        padding-left: 40px;
        line-height: 30px;
      }
    }
  }
  h3 {
    color: lightslategray;
  }
  p {
    margin-top: 15px;
  }
}
@media screen and (max-width: 500px) {
  #container {
    #about {
      width: 100vw;
      flex-direction: column;
      .part2 {
      flex-direction: column;
    }
      .second {
        margin:10px;
        padding:0px;
        line-height:1rem;
      }
      .tree {
        margin: 10px;
        padding: 0px;
        line-height:1rem;
      }
    }
    

      .jag {
        width: 100px;
        height: 100px;
        .me{
          width: 100px;
        }
      }

      
    
    .text {
      font-size: 0.7rem;
      text-align: center;
    }
  }
  .first {
      margin-bottom: 10px;
    }
    
}
</style>