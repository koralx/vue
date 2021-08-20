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
  width: 150px;
  transition: ease .2s;
  background: none;
  border: 1px black solid;
  padding: 5px;
}

.btn:hover {
  background: black;
  color: white;
}

</style>