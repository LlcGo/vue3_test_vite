<template>
<h1>一个人的信息</h1>
<h1>{{name}}</h1>
<h1>{{age}}</h1>
<h1 @click="sayHello">说话</h1>
</template>

<script>

export default {
  name: 'App',
  setup(){
    //数据
    let name = '张三'
    let age = 18
    //方法
    function sayHello(){
      alert(`我是${name},我${age}岁了`)
    }
    return{
      name,
      age,
      sayHello
    }
  }
}
</script>
