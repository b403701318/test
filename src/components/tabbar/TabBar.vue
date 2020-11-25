<template>
  <div id="tab_bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "TabBar"
}
</script>

<style scoped>
#tab_bar{
  display: flex;
  background-color: #f6f6f6;
  position: fixed;
  bottom: 0px;
  left: 0px;
  right: 0px;
  box-shadow: 0px -3px 10px rgb(100,100,.5);
}
</style>