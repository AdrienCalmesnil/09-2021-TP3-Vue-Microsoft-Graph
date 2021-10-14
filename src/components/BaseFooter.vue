<template>
  <div class="footer"><h1>Le footer</h1></div>
</template>

<script>
export default {
  name: "BaseFooter",
  data() {
    return {};
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

* {
  overflow: hidden;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


h1 {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  background-color: #222;
  color: aliceblue;
}
</style>
