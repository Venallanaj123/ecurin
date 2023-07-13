<template>
    <div>
      <child-component @message-sent="handleMessage"></child-component>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    components: {
      ChildComponent
    },
    methods: {
      handleMessage(message) {
        console.log('Message received:', message);
      }
    }
  }
  </script>
  