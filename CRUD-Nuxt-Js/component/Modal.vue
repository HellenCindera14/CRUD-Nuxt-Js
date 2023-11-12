<template>
    <div class="modal is-active">
      <div class="modal-background" @click="close"></div>
      <div class="modal-content">
        <div class="box">
          <slot name="header"></slot>
          <slot name="body"></slot>
        </div>
      </div>
      <button class="modal-close is-large" aria-label="close" @click="close"></button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      close() {
        this.$emit('close');
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add your modal styles here if needed */
  </style>
  