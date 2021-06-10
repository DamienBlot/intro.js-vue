<template>
  <button v-on:click="start">Intro.JS with Steps</button>
</template>

<script>
import introJs from "intro.js";
import "intro.js/introjs.css";

export default {
  name: "Steps",
  props: {
    options: {
      type: Object,
      require: true,
    },
  },
  methods: {
    start: function() {
      this.setOptions(this.options);
    },
    setOptions: function(options) {
      introJs()
        .setOptions(options)
        .start();
    },
  },
};
</script>

<style></style>
