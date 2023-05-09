<template>
  <p>
    This project was coded by
    <a href="https://www.lunasmithart.com/" target="_blank" class="cool-link"
      >Luna Smith</a
    >
    and is open-source on
    <a
      href="https://github.com/Lu-Smith/vue_weather_app"
      target="_blank"
      class="cool-link"
      >GitHub</a
    >.
  </p>
</template>

<style scoped>
p {
  padding: 20px 0;
  font-weight: 500;
  border-radius: 0 0 40px 40px;
}
.cool-link {
  position: relative;
  text-decoration: none;
  color: #fbf6f6;
  transition: all 0.3s ease;
  letter-spacing: 1px;
}

.cool-link:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: -5px;
  left: 0;
  background-color: #c8efde;
  visibility: hidden;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}

.cool-link:hover:before {
  visibility: visible;
  transform: scaleX(1);
}

.cool-link:hover {
  color: #c8efde;
}
</style>
