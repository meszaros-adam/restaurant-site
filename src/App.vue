<template>
  <div id="app">
    <header>Kitalált Étterem</header>
    <main>tartalom</main>
    <carouselVue></carouselVue>
    <footer> &#169; {{ year }}</footer>
  </div>
</template>

<script>
import { computed} from 'vue'
import carouselVue from './components/carousel.vue'

export default {
  name: 'app',
  components: {
    carouselVue
  },
  setup() {


    const year = computed(() => {
      return new Date().getFullYear()
    })

   

    return { year}
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@100&display=swap');

:root {
  --mainColor: #6B5E62;
  --secondaryColor: #D5CAD6;
  --shadow: 2px 2px grey;
}

body {
  font-family: 'Roboto Mono', monospace;
  background: var(--secondaryColor);
  margin: 0;
}

header {
  background: var(--mainColor);
  padding: 0, 5rem;
  text-align: center;
  font-weight: bolder;
  font-size: 50px;
  text-shadow: var(--shadow);

}

footer {
  position: absolute;
  bottom: 0px;
  background: var(--mainColor);
  width: 100vw;
  height: 3rem;
  display: grid;
  place-items: center;
  font-weight: bolder;
}
</style>
