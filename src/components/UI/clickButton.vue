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
  min-width: 100px;
  transition: ease .2s;
  background: none;
  border: 1px black solid;
  padding: 5px;
  font-size: 16px;
}

.btn:hover {
  background: black;
  color: white;
}

</style>