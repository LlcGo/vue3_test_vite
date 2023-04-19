<template>
<Demo @hello1="show" msg="你好" school="金陵科技学院">
  <template v-slot:hello>
     <span>金陵科技学院</span>
  </template>
</Demo>
</template>

<script>
import Demo  from './components/HelloWorld.vue'

export default {
  name: 'App',
  components:{Demo},
  setup(){
    function show(){
      alert('66666666')
    }
    return{
      show
    }
  }
}
</script>
