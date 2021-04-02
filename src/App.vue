<template>
  <div id="app">
    <div id="tsparticles">
      <counter
        :year="2021"
        :month="12"
        :date="24"
        :hour="10"
        :minute="10"
        :second="10"
        :millisecond="10"
        class="counter"
      ></counter>
    </div>
  </div>
</template>

<script>
import jQuery from "jquery";
const $ = jQuery;
window.$ = $;
import { tsParticles } from "tsparticles";
import counter from "./components/counter";
export default {
  name: "App",
  components: { counter },
  mounted: function () {
    tsParticles.load("tsparticles", {
      fps_limit: 60,
      interactivity: {
        detect_on: "canvas",
        events: {
          onclick: { enable: true, mode: "repulse" },
          onhover: {
            enable: true,
            mode: "bubble",
            parallax: { enable: false, force: 2, smooth: 10 },
          },
          resize: true,
        },
        modes: {
          bubble: {
            distance: 400,
            duration: 0.3,
            opacity: 1,
            size: 4,
            speed: 3,
          },
          grab: { distance: 400, line_linked: { opacity: 0.5 } },
          push: { particles_nb: 4 },
          remove: { particles_nb: 2 },
          repulse: { distance: 200, duration: 0.4 },
        },
      },
      particles: {
        color: { value: "#fff" },
        line_linked: {
          color: "#ffffff",
          distance: 500,
          enable: false,
          opacity: 0.4,
          width: 2,
        },
        move: {
          attract: { enable: false, rotateX: 600, rotateY: 1200 },
          bounce: false,
          direction: "bottom",
          enable: true,
          out_mode: "out",
          random: false,
          size: true,
          speed: 4,
          straight: false,
        },
        number: { density: { enable: true, value_area: 800 }, value: 400 },
        opacity: {
          anim: { enable: false, opacity_min: 0.1, speed: 1, sync: false },
          random: true,
          value: 0.5,
        },
        shape: {
          character: {
            fill: false,
            font: "Verdana",
            style: "",
            value: "*",
            weight: "400",
          },
          image: {
            height: 100,
            replace_color: true,
            src: "images/github.svg",
            width: 100,
          },
          polygon: { nb_sides: 5 },
          stroke: { color: "#000000", width: 0 },
          type: "circle",
        },
        size: {
          anim: { enable: false, size_min: 0.1, speed: 40, sync: false },
          random: true,
          value: 10,
        },
      },
      polygon: {
        draw: { enable: false, lineColor: "#ffffff", lineWidth: 0.5 },
        move: { radius: 10 },
        scale: 1,
        type: "none",
        url: "",
      },
      retina_detect: true,
    });
  },
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
canvas {
  display: block;
  vertical-align: bottom;
}
/* ---- tsparticles container ---- */
#tsparticles {
  position: relative;
  width: 100%;
  height: 100%;
  background-color: #000;
  background-image: url("");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50% 50%;
  top: 0;
}
.counter {
  position: absolute;
}
</style>
