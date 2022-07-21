<template>
  <div id="app">
    <header class="title">
      <h1>Vue Calculator</h1>
      <p>Build with Vue 2</p>
    </header>
    <CalculatorBody />
    <p class="sponsor">
      Developed by <a href="https://github.com/matheus-gs">@matheus-gs</a>
    </p>
  </div>
</template>

<script>
import CalculatorBody from "./main/CalculatorBody";

export default {
  components: {
    CalculatorBody,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

#app {
  width: 100%;
  height: 100vh;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  text-align: center;
  color: #dbdbdb;

  background: linear-gradient(to right, rgb(19, 106, 138), rgb(38, 120, 113));
}

#app .title {
  margin-bottom: 2em;
}

#app footer {
  display: flex;
  align-items: center;
  justify-content: center;
}
.sponsor{
  position: absolute;
  bottom: 0;
  margin-bottom: 50px
}
.sponsor a {
  color: rgb(0, 187, 255);
  text-decoration: none;
}
</style>