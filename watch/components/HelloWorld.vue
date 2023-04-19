<template>
    {{ sum }}
    <br>
    {{ sum2 }}
    <br>
    {{ x.sum3 }}
    <br>
    {{ x.sum4 }}
    <button @click="sum++">点我++</button>   
    <br>
    <button @click="sum2++">点我++</button>
    <br>
    <button @click="x.sum3++">点我1++</button>  
    <button @click="x.sum4++">点我2++</button> 
</template>
  
  <script>
  import {  ref,watch,reactive } from 'vue'
  export default {
    name:'Demo',
    // watch:{
      //  sum(O,n){
      //   console.log(O,n)
      //  }
      // sum:{
      //    immediate:true,
      //    deep:true,
      //    handler(n,o){
      //     console.log(n,o);
      //    }
      // }
    // },
    setup(){
      let sum = ref(0)
      let sum2 = ref(0)
      let x = reactive({
        sum3:0,
        sum4:0
      })
//    监视 一个 ref的数据
      // watch(sum,(n,o)=>{
      //   console.log(n,o)
      // })
      watch([sum,sum2],(n,o)=>{
         console.log('sum或者sum2变化了',n,o)
      },{immediate:true})
      
      watch(()=>x.sum3,(n,o)=>{
        console.log('x的变化',n,o)
      })

      watch([()=>x.sum3,()=>x.sum4],(n,o)=>{
        console.log('reactive',n,o)
      },{immediate:true,deep:true})
      return{
        sum,
        sum2,
        x
      }
    }
  }
  </script>
  