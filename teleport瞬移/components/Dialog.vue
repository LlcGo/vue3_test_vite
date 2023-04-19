<template>
  <div>
    <button @click="isshow = true">点弹出一个窗</button>
    <teleport to="body">
    <div v-if="isshow" class="dialog">
       <h3>我是一个弹窗</h3>
       <h4>一些内容</h4>
       <h4>一些内容</h4>
       <h4>一些内容</h4>
       <h4>一些内容</h4>
       <button @click="isshow = false">关闭弹窗</button>
    </div>
    </teleport>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  name:'Dialog',
  setup(){
    let isshow = ref(false);
    // function show(){
    //   isshow.value = !isshow.value
    // }
    return {isshow}
  }
}
</script>

<style>
.dialog{
    width: 300px;
    height: 300px;
    background: green;
}
</style>

 