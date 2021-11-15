<template>
  <HelloWorld msg="Caribbean Courtyard Villa" />
</template>

<script>
import HelloWorldVue from "./components/Lighting.vue";

export default {
  name: "App",
  components: {
    HelloWorld: HelloWorldVue,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Rubik");

#app {
  font-family: "Rubik", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ddd;
  margin-top: 160px;
}
</style>
