<template>
 <input type="text" v-model="keyword">
 <h3>{{ keyword }}</h3>
</template>

<script>
import { clearTimeout } from 'timers';
import { setTimeout } from 'timers/promises';
import { ref,customRef } from 'vue'; 
export default {
  name: 'App',
  setup(){
    //自定义一个ref
    function myRef(value,delay){
      let timer
        return customRef((track,tigger)=>{
          return{
            get(){
             track() //通知vue追踪vule变化
             return value //3
            },
            set(newValue){
              clearTimeout(timer)
              timer = setTimeout(() => {
                value = newValue  //1
                tigger()  //2 通知vue解析模板
              }, delay)
            }
          }
        })
    }
  // let keyword = ref('hello')
  //自定义ref
  let keyword = myRef('hello',500)
  return {keyword}
  }
}
</script>
