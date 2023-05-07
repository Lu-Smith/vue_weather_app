<template>
  <div id="app">
    <main>
      <h1>Weather App</h1>
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
  margin: 20px;
  background-color: rgb(124, 172, 190);
}

#app {
  background-image: url("./assets/cold-bg.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s all ease-in-out;
  border-radius: 40px;
}

main {
  min-height: 100vh;
  border-radius: 40px;
  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.15),
    rgba(0, 0, 0, 0.55)
  );
}

h1 {
  padding: 40px 0;
}
</style>
