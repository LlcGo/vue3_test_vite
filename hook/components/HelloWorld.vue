<template>
    <h2>坐标:x ={{p.x}} y={{p.y}}</h2>   
</template>
  
  <script>
  import {  reactive,onMounted,onBeforeUnmount } from 'vue'
  import point from '../hook/usePoint'
  export default {
    name:'Demo',
    setup(){
      let p  = point()
      return{
        p
      }
    }
  }
  </script>
  