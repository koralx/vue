<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {

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
</style>