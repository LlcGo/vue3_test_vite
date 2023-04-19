<template>
<h1>{{ person.name }}</h1>
<h1>{{ person.age }}</h1>
<button @click="setValue">修改数据</button>
<h1>{{ person.job.type }}</h1>
<h1>{{ person.job.salary }}</h1>
<h1>{{ person.hobby }}</h1>
</template>

<script>
import { reactive } from 'vue'


export default {
  name: 'App',
  setup(){
    //数据
    // let name = ref('张三')
    // let age = ref(18)
    // let job = ref({
    //   type:'UI工程师',
    //   salary:'20k'
    // })

    let person = reactive({
      name:'张三',
      age: 18,
      job:{
        type:'UI工程师',
        salary:'20k'
      },
      hobby:['抽烟','喝酒','烫头']
    })
    //方法
    function setValue(){
        // job.value.type = 'UI设计师'
        // job.value.salary = '30k'
        person.age = 19
        person.name = '小王',
        person.job.type = 'UI设计师'
        person.job.salary = '30k'
        person.hobby[0] = '睡觉'
    }
    return{
      person,
      setValue
    }
  }
}
</script>
