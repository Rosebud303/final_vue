<template>
  <div id="app">
    {{msg}}
    <Images v-bind:msg="msg"/>
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
      msg: 'Helloz'
    }
  }
}
</script>

<style>
#app {

}
</style>
