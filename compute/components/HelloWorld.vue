<template>
   姓: <input type="text" v-model="person.fristName">
   <br>
   名: <input type="text" v-model="person.endName">
   <br>
   姓名：{{ person.fullName }}
   <br>
   姓名：<input type="text" v-model="person.fullName">
</template>
  
  <script>
  import { reactive,computed } from 'vue'
  export default {
    name:'Demo',
    // computed:{
    //      fullName(){
    //       return this.person.fristName + this.person.endName
    //      }
    // },
    setup(){
      let person = reactive({
        fristName:'张',
        endName: '三',
      })

      // person.fullName = computed(() =>{
      //   return person.fristName + '-' + person.endName
      // })
      //完整写法
      person.fullName = computed({
        get(){
          return person.fristName + '-' + person.endName
        },
        set(value){
           const s = value.split('-');
           person.fristName = s[0];
           person.endName = s[1];
        }
      })
      return{
        person,
      }
    }
  }
  </script>
  