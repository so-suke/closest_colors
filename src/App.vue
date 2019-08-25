<template>
  <div id="app">
    <div class="box" v-bind:style="{ backgroundColor: activeColor }"></div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
let convert = require("color-convert");

export default {
  name: "app",
  data() {
    return {
      activeColor: 'rgb(200, 0, 0)',
    }
  },
  components: {
    HelloWorld
  },
  mounted() {
    const converted = convert.hex.rgb("FF0000");
    console.log(converted);
    converted[0] += 1;
    let h = convert.rgb.hex(255, 0, 0);
    console.log(h);
    // this.$refs.box.css();
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.box {
  width: 100px;
  height: 100px;
  /* background-color: blue; */
}
</style>
