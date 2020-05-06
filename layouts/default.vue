<template>
  <div class="default-page">
    <navbar/>
    <nuxt/>
  </div>
</template>

<script>
  import Navbar from "../components/Navbar"

  export default {
    components: {Navbar}
  }
</script>

<style>
/*  ::-webkit-scrollbar {
    width: 12px;
  }

  ::-webkit-scrollbar-track {
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
    border-radius: 10px;
  }

  ::-webkit-scrollbar-thumb {
    border-radius: 10px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.5);
  }*/

  body {
    font-family: '1';
  }

  h1 {
    margin: 0;
    padding: 0;
  }

  .default-page {
    overflow: hidden;
    padding: 0 10px;
  }

  a {
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
</style>
