<template>
  <div id="contact">
    <h2>Contact me</h2>
    <h3>Email: lijuancheng12@gmail.com</h3>

    <div>
      <a href="https://github.com/lijuancheng12">
        <img src="@/assets/github.png" class="social" />
      </a>
      <a href="https://www.linkedin.com/in/lijuan-cheng-39ba77191/">
        <img src="@/assets/linkedin.png" class="social" />
      </a>
    </div>
    <VueElevator
      :word="word"
      :duration="duration"
      :mainAudio="mainAudio"
      :endAudio="endAudio"
    ></VueElevator>
  </div>
</template>

<script>
import music from "../assets/music.mp3";
export default {
  data() {
    return {
      // Replace word, duration, mainAudio and endAudio setting as you want.
      // If default is what you like, just don't use related key-value pair and ignore it.
      word: "Go to Top",
      duration: 45000,
      mainAudio: music,
      endAudio: "http://tholman.com/elevator.js/music/ding.mp3",
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";
#contact {
  width: 1200px;
  height: 100vh;
  margin: 500px auto 0px auto;
  color: $white;
  font-size: 2rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  h2 {
    margin-top: 20px;
  }
  .social {
    width: 30px;
    background-color: $white;
    margin: 20px;
  }
}
#contact::v-deep .elevator-button {
  width: 20%;
  border-radius: 10px;
  cursor: pointer;
  margin: auto;
  background: white;
  color: #000;
  font-family: "Fredoka One", cursive;
  font-weight: bold;
}
@media screen and (max-width: 500px) {
  #contact {
    width: 100vw;
    font-size: 1rem;
  }
}
</style>