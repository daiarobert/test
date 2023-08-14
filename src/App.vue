<template>
  <CardComponent />
</template>

<script>
import CardComponent from "./components/CardComponent.vue";

export default {
  name: "App",
  components: {
    CardComponent,
  },
};
</script>

<style>
#app {
  font-family: "Source Sans Pro", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
* {
  margin: 0;
  padding: 0;
}
</style>
