<template>
  <div id="app">
    <div class="page-container">
      <div class="content-wrap">
        <header>Kitalált Étterem</header>
        <navVue></navVue>
        <main>
          <carouselVue></carouselVue>
          <openingVue></openingVue>
          <menuVue></menuVue>
          <contactVue></contactVue>
        </main>
      </div>
      <footer> &#169; {{ year }}</footer>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
import carouselVue from './components/carousel.vue'
import navVue from './components/nav.vue'
import openingVue from './components/opening.vue'
import contactVue from './components/contact.vue'
import menuVue from './components/menu.vue'
export default {
  name: 'app',
  components: {
    carouselVue,
    navVue,
    openingVue,
    contactVue,
    menuVue,
  },
  setup() {


    const year = computed(() => {
      return new Date().getFullYear()
    })

    return { year }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@100&display=swap');

:root {
  --mainColor: #6B5E62;
  --secondaryColor: #D5CAD6;
  --tertiaryColor: #84757a;
  --shadow: 2px 2px grey;
  --borderRadius: 2rem;
  font-weight: bolder;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Roboto Mono', monospace;
  background: var(--secondaryColor);
  margin: 0;
}

h1 {
  margin-bottom: 5rem;
  font-size: 50px;
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
  bottom: 0;
  background: var(--mainColor);
  width: 100%;
  height: 2.5rem;
  display: grid;
  place-items: center;
  font-weight: bolder;
}

main {
  padding-bottom: 100vh;
}

.page-container {
  position: relative;
  min-height: 100vh;
}

.content-wrap {
  padding-bottom: 2.5rem;
  /* Footer height */
}

/* Utlities */

.center {
  display: grid;
  place-content: center;
}

.container{
  margin: 3rem;
  padding: 3rem;
}
</style>
