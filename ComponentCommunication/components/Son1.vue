<template>
  <div id="son1">Son1:{{value}}</div>
</template>
<script>
export default {
  name: "Son1",
  props: {
    value: {
      type: Number,
      default: 0
    }
  }
};
</script>