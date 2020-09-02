<template>
  <div class="image-container">
    <img :src="picture.picture" class="bild" :title="picture.description" @click="big = !big" />
    <a :href="picture.url" class="click">
      <div class="button">{{picture.title}}</div>
    </a>
  </div>
</template>

<script>
export default {
  props: ["picture"]
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";
@import url("https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap");

.image-container {
  display: flex;
  flex-direction: column;
  margin-bottom:20px;

  .bild {
    background-color: white;
    width: 350px;
    height: 350px;
    object-fit: contain;
    margin: 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
  .click {
    text-decoration: none;
    text-align: center;
    font-family: "Fredoka One", cursive;

    color:$white;
  }
 
}
.click:hover{
  color: $yellow;
    
  }
  @media screen and (max-width: 500px) {
    .image-container .bild{
      width: 250px;
     height: 250px;
    }
    .image-container {
      margin: auto;
    }
  
    }

</style>