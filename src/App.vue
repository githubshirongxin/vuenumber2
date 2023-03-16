<script setup>
    import Num2 from './components/number-animation2/Num2.vue'
</script>

<template>
  <num2  
   :start="21" 
   :end="979" 
   :speed="51" 
   :ticks="21" 
   theme='car' ></num2>
</template>

<style >

 body {
    box-sizing: border-box;
    margin: 0px;
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    border:1px solid blue;
 }
</style>
