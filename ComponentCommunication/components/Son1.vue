<template>
  <div id="son1">
    Son1:{{value}}
    <p>$emit</p>
    <div>
      <input type="text" @input="change" v-model="value" />
    </div>
  </div>
</template>
<script>
export default {
  name: "Son1",
  props: {
    value: {
      type: Number,
      default: 0
    }
  },
  methods: {
    change() {
      this.$emit("input",this.value)
    }
  }
};
</script>