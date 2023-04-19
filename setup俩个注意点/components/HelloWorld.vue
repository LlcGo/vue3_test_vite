<template>
  <h1>{{ person.name }}</h1>
  <h1>{{ person.age }}</h1>
  <h1>{{ msg }}</h1>
  <h1>{{ school }}</h1>
  <slot name="hello"></slot>
  <button @click="test">显示信息</button>
</template>
  
  <script>
  import { reactive } from 'vue'
  
  export default {
    name: 'Demo',
    props:['msg','school'],
    emits:['hello','hello1'],
    setup(props,context){
      console.log('props',props)
      console.log('context.attrs',context.attrs)
      // console.log('context.slots',context.slots)
      console.log('context.emit',context.emit)
      let person = reactive({
        name:'张三',
        age: 18,
      })
      function test(){
        context.emit('hello1')
      }

      return{
        person,
        test
      }
    }
  }
  </script>
  