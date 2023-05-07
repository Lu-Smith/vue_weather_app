<template>
  <div id="app">
    <h1>Weather App</h1>
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search..." />
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  // data() {
  //   return;
  //   {
  //     api_key: "066ad54b2cd3c41c1bb7a8f3fc5f5ed0";
  //   }
  // },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin: 60px;
}

#app {
  background-image: url("./assets/cold-bg.jpg");
}
</style>
