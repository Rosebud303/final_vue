<template>
  <div>
    <div v-for="image in allImages" class="all-images">
      <p class='rendition'>Rendition Number: {{image.renditionnumber}}</p>
      <img class='image' v-bind:src="image.baseimageurl"/>
    </div>
  </div>
</template>

<script>
import apikey from '../../api'

export default {
  name: "Images",
  props: ["msg"],

  data() {
    return {
      allImages: []
    }

  },
  methods: {

  },
  mounted() {
    fetch(`https://api.harvardartmuseums.org/image?apikey=${apikey}`)
      .then(response => response.json())
      .then(result => this.allImages = result.records)
  }
}
</script>

<style scoped>

</style>
