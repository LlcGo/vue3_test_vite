<template>
 <div class="app">
  <h3>我是app组件(祖),</h3>
  <Suspense>
  <template v-slot:default>
     <child/>
  </template>
  <template v-slot:fallback>
     <h3>加载中...</h3>
  </template>
  </Suspense>
 </div>
</template>

<script>
// import child from './components/Child.vue'静态引入
import { defineAsyncComponent } from 'vue' //动态映入
const child = defineAsyncComponent(()=>import('./components/Child.vue'))
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
