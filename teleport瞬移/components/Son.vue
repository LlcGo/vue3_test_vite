<template>
    <div class="son">
     <h3>我是son组件(孙) </h3>
     <Dialog/>
    </div>
   </template>
   
   <script>
     import Dialog from './Dialog.vue'
     export default{
       name:'son',
       components:{Dialog}
     }
   </script>
   
   <style>
     .son{
       background-color: orange;
       padding: 10px;
     }
   </style>