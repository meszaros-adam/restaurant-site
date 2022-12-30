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
      <footer>
        <div>&#169; {{ year }}</div>
        <div>Kitalált Étterem</div>
      </footer>
      <i @click="scrollUp" class="bi bi-arrow-up-circle-fill hide" id="up-arrow"></i>
    </div>
  </div>
</template>

<script>
import { computed, onMounted } from 'vue'
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

    const scrollUp = () => {
      window.scrollTo(0, 0);
    }

    let upArrowId = null;

    onMounted(() => {
      upArrowId = document.getElementById("up-arrow")
    })


    const scrollFunc = () => {
      const y = window.scrollY
      if (y > 800) {
        upArrowId.className = "bi bi-arrow-up-circle-fill show"
      } else {
        upArrowId.className = "bi bi-arrow-up-circle-fill hide"
      }
    }

    window.addEventListener("scroll", scrollFunc)

    return { year, scrollUp }
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
  --footerHeight: 3rem;
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
  height: var(--footerHeight);
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
  padding-bottom: var(--footerHeight)
    /* Footer height */
}

/* Utlities */

.center {
  display: grid;
  place-content: center;
}

.container {
  margin: 3rem;
  padding: 3rem;
}

/* up arrow */
#up-arrow {
  position: fixed;
  right: 2rem;
  bottom: 2rem;
  font-size: 2rem;
  cursor: pointer;
  transition: all ease 1s;
}

#up-arrow:hover {
  color: #3C4048;
}

.hide {
  opacity: 0;
  left: -100%;
}

.show {
  opacity: 1;
}
</style>
