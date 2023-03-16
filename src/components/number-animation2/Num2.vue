<script setup>
import {reactive, ref} from 'vue'
const props = defineProps(['start','end','speed','ticks','theme'])

const count  = ref(0);


let start = props.start || 10;
let end = props.end || 968 ;
let ticks = props.ticks|| 20;
let speed = props.speed || 50;
let theme = props.theme ;

let randomNumbers = [end]

for (let i = 0; i < ticks - 1; i++) {
  randomNumbers.unshift(
    Math.floor(Math.random() * (end - start + 1) + start)
  );
}

randomNumbers.sort((a, b) => {return a - b});



let x = 0;


// let haha = 0;
let interval = setInterval( ()=> {
    count.value = randomNumbers.shift();
    if (++x === ticks) {
        window.clearInterval(interval);
    }
}, speed);

var styleObject = reactive({});
console.log("theme = "+theme);
if(theme == "default"){
    console.log("default theme.");
    styleObject =  {
        display: "inline-block",
        background: "blue",
        width: "200px",
        height:"100px",
        padding: "2px",
        color:"black",
         fontSize: "5rem",
        fontWeight: "bold",
        "font-family": "helvetica",
        "text-align": "center",
        color: "white"
    }
}else if(theme == "car"){
    console.log(" car theme.");
    styleObject =  {
        display: "inline-block",
         background: "red",
        width: "200px",
        height:"100px",
        padding: "2px",
        color:"black",
         fontSize: "5rem",
        fontWeight: "bold",
        "font-family": "helvetica",
        "text-align": "center",
        color: "white"
    }
}else{
console.log("dont konow theme.");
}




</script>
<template>
    <div  :style="styleObject"> {{ count }} </div>
</template>



<style scoped>
.bounchNum { 
 display: inline-block;
  background: crimson; 
  width: auto;
  height:auto;
  padding: 2px;
  font-size: 5rem;
  font-weight: bold;
  font-family: helvetica;
  text-align: center;
  color: white;
  margin-top: 100px;
}

</style>