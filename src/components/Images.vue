<template>
  <div class="all-images">
    <div v-for="image in allImages" class='image-container'>
      <p class='rendition'>Rendition Number: {{image.renditionnumber}}</p>
      <img class='image' v-bind:src="image.baseimageurl"/>
    </div>
  </div>
</template>

<script>
import { apiKey } from '../../api'

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
    fetch(`https://api.harvardartmuseums.org/image?apikey=${apiKey}`)
      .then(response => response.json())
      .then(result => this.allImages = result.records)
      .catch(error => console.log(error))
  }
}
</script>

<style scoped>
  .all-images {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    flex-direction: row;
  }

  .image-container {
    margin: 10px;
    padding: 20px;
    display: flex;
    align-items: center;
    flex-direction: column;
    width: 20%;
    background-color: #673ab7;
    transition: .8s;
  }

  .image-container:hover {
    background-color: #3f51b5;
    color: white;
    box-shadow: 10px 10px 6px black;
    cursor: pointer;
  }

  .image {
    width: 80%;
    opacity: .9;
  }
</style>
