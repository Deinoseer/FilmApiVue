<template>
  <div id="app">
    <div class="header">
      <p class="">#Movienow</p>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
}
#app {
  background-color: #363232;
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  //text-align: center;
  color: #2c3e50;
  min-height: 50vw;
}
.header {
  width: 100%;
  height: 100px;
  background-color: #fa2828;

  p {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 48px;
    line-height: 96px;
    text-align: center;
    letter-spacing: 0.21em;
    text-transform: uppercase;
    margin: auto;
    vertical-align: middle;
    color: black;
  }
}
</style>
