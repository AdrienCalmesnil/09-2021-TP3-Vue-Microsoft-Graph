<template>
    <div class="button">
        <button id='but_disabled' v-if="disable" disabled><slot></slot></button>
        <button id='but_activate' v-else><slot></slot></button>
    </div>
</template>

<script>
export default {
  name: "BaseButton",
  disable : false,
  props:{
      disable: {type: Boolean},
  },
  data(){
      return{}
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
    margin: 0;
    padding: 0;
    box-sizing:  border-box;
}

/* .button{
    width: 100px;
    height: 100px;
    background: red;
} */

button{
    padding: 15px 40px;
    background: none;
    border-radius: 10px;
    border: #BADA55;
    background: #BADA55;
    color: #2c3e50;
    margin: 15px 0;
    font-size: 1.5em;
    font-weight: bold;
}

#but_activate:hover{
    background: white;
    color: #2c3e50;
    border: 2px solid #BADA55;
}

button:focus{
    background: red;
}

#but_disabled{
    background: #7a971a;
}

#but_disabled:hover{
    background: white;
    color: #2c3e50;
    border: 2px solid #7a971a;
}

</style>

