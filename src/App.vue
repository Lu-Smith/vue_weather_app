<template>
  <div id="app">
    <main>
      <h1>Weather App</h1>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search..." />
      </div>
      <div class="weather-wrap">
        <div class="location-box">
          <div class="location">Edinburgh, UK</div>
          <div class="date">Monday 20 January 2023</div>
        </div>
        <div class="weather-box">
          <div class="temperature">0℃</div>
          <div class="weather">Rain</div>
        </div>
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

.search-box {
  display: flex;
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar {
  display: block;
  width: 80%;
  text-align: center;
  margin: 0 auto;
  padding: 15px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  background: none;
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 0 16px 0 16px;
  transition: 0.4s ease-in-out;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.25);
}

.search-box .search-bar:focus {
  background-color: rgba(255, 255, 255, 0.75);
  box-shadow: 0 0 16px rgba(0, 0, 0, 0.25);
  border-radius: 16px 0 16px 0;
}

.location-box .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-shadow: 1px 2px rgba(0, 0, 0, 0.2);
}

.location-box .date {
  margin-top: 10px;
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
}

.weather-box .temperature {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
}
</style>
