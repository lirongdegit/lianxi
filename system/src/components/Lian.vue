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
  name: 'Lian',
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
}
.hello-enter-active{
  animation: feichu 0.5s linear;
}
.hello-leave-active{
  animation: feichu 0.5s reverse;
}
@keyframes feichu {
  from{
    transform: translateX(-100%);
  }
  to{
    transform: translateX(0px);
  }
}
</style>
