<template>
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
     <transition name="hello" appear>
      <h1 v-show="isShow">你好啊</h1>
     </transition>
    </div>
    
  </template>
  
  <script>
  export default {
    name: 'Lian2',
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
  .hello-enter-active, .hello-leave-active{
    transition: 0.5s linear; 
  }

  .hello-enter,.hello-leave-to {
    transform: translateX(-100%);
  }
  .hello-leave.hello-enter-to{
    transform: translateX(0);
  }
 
  </style>
  