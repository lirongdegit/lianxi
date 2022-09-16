<template>
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
     <transition-group 
     appear
     name="animate__animated animate__bounce" 
     enter-active-class="animate__backInDown"
     leave-active-class="animate__fadeOutUp"
     >
      <h1 v-show="!isShow" key="1">你好啊</h1>
      <h1 v-show="isShow" key="2">李蓉</h1>
     </transition-group >
    </div>
    
  </template>
  
  <script>
  import 'animate.css'
   export default {
    name: 'Lian3',
    data(){
      return{
        isShow:true
      }
    },
    
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  h1{
    background-color: orange;
    /* transition: 0.5s linear; */
  }
  
 
  </style>
  