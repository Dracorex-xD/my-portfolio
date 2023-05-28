<template>
    <div class="heading">
      {{ heading }}
    </div>
  </template>
  
  <script>
  export default {
    name: 'heading',
    props: {
      heading: {
        type: String,
        required: true
      }
    }
  }
  </script>
  
  <style scoped>
  .heading {
    font-weight: 700;
    font-size: 4rem;
    color: var(--secondary-button-color);
    border-bottom: 1px var(--accent-color) solid;
    margin: 1rem;
    padding-bottom: 1rem;
  }
  </style>
  