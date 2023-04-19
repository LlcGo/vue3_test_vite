<template>
 <div class="app">
  <h3>我是app组件(祖),{{ name }} -- {{ price }}</h3>
  <child/>
 </div>
</template>

<script>
import child from './components/Child.vue'
import { reactive,toRefs,provide } from 'vue';  
export default{
    name:'App',
    components:{child},
    setup(){
     let car = reactive({name:'奔驰',price:'40w'})
     provide('car',car)//给自己的后代传输
     return {...toRefs(car)}
    }
  } 
</script>

<style>
  .app{
    background-color: gray;
    padding: 10px;
  }
</style>
