<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'click-button'
}
</script>

<style scoped>
.btn {
  min-width: 40px;
  height: 40px;
  transition: ease .2s;
  background: none;
  border: 0px;
  border-radius: 5px;
  border: 1px solid black;
  padding: 5px;
  font-size: 16px; 
}

.btn:hover {
  background: black;
  color: white;
}

</style>