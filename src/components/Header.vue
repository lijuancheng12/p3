<template>
  <nav id="nav">
    <ul>
      <li>
        <a href="#home">Hem</a>
      </li>
      <li>
        <a href="#portfolio">Portfolio</a>
      </li>
      <li>
        <a href="#about">Om mig</a>
      </li>
      <li>
        <a href="#contact">Kontakt</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap");
@import "../assets/scss/main.scss";
#nav {
  position: fixed;
  top: 0;
  z-index: 1;
  display: flex;
  width: 100%;
  height: 10%;
  background-color: $pink;
  ul {
    display: flex;
    list-style: none;
    width: 100%;
    justify-content: center;
    li {
      margin: 0 1rem;
      padding: 0rem;
      a {
        text-decoration: none;
        font-family: "Fredoka One", cursive;
        text-transform: uppercase;
        color: rgb(240, 240, 74);
        font-size: 20px;
        font-weight: bold;
      }
    }
  }
}
#nav ul li a:hover {
  color: $white;
}

@media screen and (max-width: 500px) {
  #nav {
    max-width: 100%;

    ul {
      padding: 0px;
      margin: 0px;
    }
    ul li a {
      font-size: 12px;
    }

    width: 100vw;
    height: 100px;
    font-size: 5px;
  }
}
</style>