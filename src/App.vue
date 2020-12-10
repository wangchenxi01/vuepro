<script type="text/javascript" src="./js/sakura.js"></script>
<template>
  <div id="app" style="width: 100%;height: 100%;">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <img alt="pic1" src="./assets/pic1.jpg" width="100%" style="margin-top: -100px;">
    <div style="margin-top: -500px; background-color: aliceblue;">
      <HelloWorld msg="Welcome to my first vue page"/>
      <h1  style="color:blue; margin-top: 100px;">comming soon</h1>
      <footer><div style="text-align: right;">ver 1.0</div></footer>
    </div>
    
  </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
