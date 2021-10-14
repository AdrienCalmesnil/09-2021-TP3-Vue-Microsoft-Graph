<template>
<div class="wrapper"><h1>Le header</h1></div>
  
</template>

<script>
export default {
  name: "BaseHeader",
  data(){
      return{

      }
  }
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

*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}

.wrapper{
  width: 100vw;
}

h1{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
  background-color: #bada55;
}
</style>
