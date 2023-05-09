<template>
  <div
    id="app"
    :class="
      typeof weather.main != 'undefined' && weather.main.temp > 16 ? 'hot' : ''
    "
  >
    <main>
      <h1>Weather App</h1>
      <div class="search-box">
        <input
          type="text"
          class="search-bar"
          placeholder="Search..."
          v-model="query"
          @keypress="fetchWeather"
        />
      </div>
      <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
        <div class="location-box">
          <div class="location">
            {{ weather.name }}, {{ weather.sys.country }}
          </div>
          <div class="date">{{ dateBuilder() }}</div>
        </div>
        <div class="weather-box">
          <div class="temperature">{{ Math.round(weather.main.temp) }}℃</div>
          <div class="weather">{{ weather.weather[0].main }}</div>
          <div class="wind">{{ weather.wind.speed }}</div>
        </div>
      </div>
    </main>
    <footerApp />
  </div>
</template>

<script>
import footerApp from "./components/footerApp.vue";

export default {
  name: "App",
  components: {
    footerApp,
  },
  data() {
    return {
      api_key: "066ad54b2cd3c41c1bb7a8f3fc5f5ed0",
      url_base: "https://api.openweathermap.org/data/2.5/weather?",
      query: "",
      weather: {},
    };
  },
  methods: {
    fetchWeather(e) {
      if (e.key == "Enter") {
        fetch(
          `${this.url_base}q=${this.query}&appid=${this.api_key}&units=metric`
        )
          .then((res) => {
            return res.json();
          })
          .then(this.setResults)
          .catch((error) => {
            console.error(error);
          });
      }
    },
    setResults(results) {
      this.weather = results;
      console.log(results);
    },
    dateBuilder() {
      let d = new Date();
      let months = [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December",
      ];
      let days = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];

      let day = days[d.getDay()];
      let date = d.getDate();
      let month = months[d.getMonth()];
      let year = d.getFullYear();

      return `${day}, ${date} ${month} ${year} `;
    },
  },
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
}

#app {
  background-image: url("./assets/cold-bg.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s all ease-in-out;
  border-radius: 40px 40px 0 0;
}

#app.hot {
  background-image: url("./assets/hot-bg.jpg");
}

main {
  min-height: 100vh;
  border-radius: 40px 40px 0 0;
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
  font-size: 102px;
  font-weight: 900px;

  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box .weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 1px 5px rgba(0, 0, 0, 0.2);
}
</style>
