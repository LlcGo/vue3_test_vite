<template>
 <div class="app">
  <h3>我是app组件(祖),</h3>
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
    
    }
  } 
</script>

<style>
  .app{
    background-color: gray;
    padding: 10px;
  }
</style>
