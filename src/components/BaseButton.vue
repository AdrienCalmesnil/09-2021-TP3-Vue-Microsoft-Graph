<template>
    <div class="button">
        <button :style="cssProps" id='but_disabled' v-if="disable" disabled><slot></slot></button>
        <button :style="cssProps" id='but_activate' v-else><slot></slot></button>
    </div>
</template>

<script>
export default {
    name: 'BaseButton',
    disable: false,
    color: "primary",
    props:{
        disable:{ type:Boolean },
        color:{ type:String }
    },
    data(){
        const data = {
           primary : {bg:"#50DB56", hvbg:"#8AE38E", fcbg:"#00EE0B"},
           warn : {bg:"#FF5733",hvbg:"#FF6645", fcbg:"#FF7C60"},
           danger : {bg:"#FF0000",hvbg:"#FF3E3E", fcbg:"#B20000"}
        };
        return {
            data
        };
    },
    computed: {
        cssProps(){
            return {
                "--background-color": this.data[this.color].bg,
                "--background-color-hover": this.data[this.color].hvbg,
                "--background-color-focus": this.data[this.color].fcbg
            }
        }
    },
     watch:{
        color: {
            cssProps(){
            return {
                "--background-color": this.data[this.color].bg,
                "--background-color-hover": this.data[this.color].hvbg,
                "--background-color-focus": this.data[this.color].fcbg
                }
            }
        }
    }
}
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

button{
    padding: 15px 40px;
    background: none;
    border-radius: 10px;
    border: #BADA55;
    background-color: var(--background-color);
    color: #2c3e50;
    margin: 15px 0;
    font-size: 1.5em;
    font-weight: bold;
}

#but_activate:hover{
    background-color: var(--background-color-hover);
    color: #2c3e50;
}

button:focus{
    background-color: var(--background-color-focus);
}

#but_disabled{
    background: #7a971a;
}

#but_disabled:hover{
    background-color: #688113;
    color: #2c3e50;
}


</style>

