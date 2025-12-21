<template>
  <div id="ola-map">
    <Actions />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { OlaMaps } from 'olamaps-web-sdk'

let lat = ref(40.689247)
let lng = ref(-74.044502)

const token = 'P2Ffje9TtXz9Nam3Bd5rMHLTMTOoi96bE2RiVdAg'

let myMap = null

onMounted(() => {
  const olaMaps = new OlaMaps({
    apiKey: token,
  })

  myMap = olaMaps.init({
    style: 'https://api.olamaps.io/tiles/vector/v1/styles/default-light-standard/style.json',
    container: 'ola-map',
    center: [lng.value, lat.value], // Initial center set to the default coordinates
    zoom: 15,
  })
})
</script>

<style scoped>
#ola-map {
  width: 100vw;
  height: 100vh;
}
</style>
