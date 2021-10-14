<template>
  <div>
    <BaseLayout>
      <HomePage />
    </BaseLayout>    
  </div>
</template>

<script>
import HomePage from "./pages/HomePage.vue";
import BaseLayout from "./components/BaseLayout.vue"

export default {
  name: "App",
  components: {
    HomePage,
    BaseLayout,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0px;
}
</style>
