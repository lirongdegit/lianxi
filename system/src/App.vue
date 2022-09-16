<template>
  <div>
    <Lian/>
    <Lian2/>
    <lian3/>
  </div>
</template>

<script>
import axios from 'axios'
import Lian from './components/Lian'
import Lian2 from './components/Lian2';
import Lian3 from './components/Lian3';

export default {
  name: 'App',
  components: {
    Lian,
    Lian2,
    Lian3
   
}
}
</script>

<style>


</style>
