<template>
  <div id="skill">
    I know <span v-html="skill">{{ skill }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        "Vue, React, HTML, CSS, JavaScript, TypeScript, PWA, SASS, Node.js, MySQL",
      ],
      colors: [
        "purple",
        "white",
        "orange",
        "FUCHSIA",
        "blue",
        "red",
        "green",
        "yellow",
        "turquoise",
      ],
      skill: "",
      current: 0,
      counter: 0,
      up: true,
      activeColor: 0,
    };
  },
  methods: {
    write() {
      let current = this.skills[this.current];
      let timeout = 200;
      if (this.up) {
        if (this.counter < current.length) {
          this.counter++;
        } else {
          this.up = false;
        }
      } else {
        if (this.counter >= 0) {
          this.counter--;
          timeout = 50;
        } else {
          this.up = true;
          this.counter = 0;
          this.current = (this.current + 1) % this.skills.length;
          current = this.skills[this.current];
        }
      }
      this.skill = this.addColor(current.substring(0, this.counter));
      window.setTimeout(this.write, timeout);
    },
    addColor(text) {
      return text
        .split(",")
        .map(
          (word, index) =>
            `<span style="color:${this.colors[index]}">${word}</span>`
        )
        .join(",");
    },
  },
  mounted() {
    this.write();
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";
#skill {
  margin: auto;
  color: $pink;
  font-size: 20px;
}
@media screen and (max-width: 500px) {
  #skill {
    margin-top: 20px;
  }
}
</style>