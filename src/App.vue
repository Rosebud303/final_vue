<template>
  <div id="app">
    <h1>{{msg}}</h1>
    <Images />
  </div>
</template>

<script>
import Images from './components/Images'

export default {
  name: 'app',
  components: {
    Images
  },
  data() {
    return {
      msg: 'Gallery'
    }
  }
}
</script>

<style>
#app {
  font-family: cursive;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  background-image: url('https://i.imgur.com/ffa5IVO.jpg');
  background-attachment: fixed;
  background-position: center; 
}
</style>
