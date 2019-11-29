<template>
  <div id="parent">
    parent：{{money}}
    <Son1 :value="money"/>
  </div>
</template>
<script>
import Son1 from "./Son1";
export default {
  name: "Parent",
  components: { Son1 },
  data() {
    return {
      money: 100
    };
  }
};
</script>