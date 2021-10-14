<template>
  <div>
    <BaseLayout>
      <HomePage />
      <BaseButton :disable="false" color="primary">Button</BaseButton>
      <BaseButton :disable="true" color="primary">Button Disabled</BaseButton>
      <BaseButton :disable="false" color="warn">Button Warn Color</BaseButton>
      <BaseButton :disable="false" color="danger">Button Danger Color</BaseButton>
      <AsyncButton :disable="false" color="primary">AsyncButton</AsyncButton>
    </BaseLayout>
    
  </div>
</template>

<script>
import HomePage from "./pages/HomePage.vue";
import BaseLayout from "./components/BaseLayout.vue";
import BaseButton from "./components/BaseButton.vue";
import AsyncButton from "./components/AsyncButton.vue"

export default {
  name: "App",
  components: {
    HomePage,
    BaseLayout,
    BaseButton,
    AsyncButton,
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
