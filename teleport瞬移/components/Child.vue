<template>
    <div class="child">
     <h3>我是child组件(子) </h3>
     <son/>
    </div>
   </template>
   
   <script>
    import son from './Son.vue'
     export default{
       name:'child',
       components:{son}
     }
   </script>
   
   <style>
     .child{
       background-color: skyblue;
       padding: 10px;
     }
   </style>
   