<template>
  <div id="app">

    <Header />

    <main>

      <DiskList />

    </main>

  </div>
</template>

<script>
import Header from "./components/Header.vue";
import DiskList from "./components/DiskList.vue";

export default {
  name: "App",
  components: {
    Header,
    DiskList,
  },
};
</script>

<style lang="scss">

  /* RESET */

  *{

    margin: 0;
    padding: 0;
    box-sizing: border-box;

  }

  body{

    font-family: 'Roboto', sans-serif;

  }

  main{

    background-color: #1e2d3b;
    width: 100%;
    height: calc( 100vh - 70px );

  }

  

</style>
