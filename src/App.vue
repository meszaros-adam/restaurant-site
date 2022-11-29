<template>
  <div id="app">
    <header>Az én éttermem</header>
    <main>tartalom</main>
    <footer>Lábléc</footer>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
  }
}
</script>

<style>
body {
  background: #1F2F16;
  margin: 0;
}
header{
  background: #5E5C6C;
  padding: 1rem;
}
footer {
  position: absolute;
  bottom: 0px;
  background: #5E5C6C;
  width: 100vw;
  height: 3rem;
  display: grid;
  place-items: center;
}
</style>
