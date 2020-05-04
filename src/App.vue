<template>
  <div id="app">
    <Comments />
  </div>
</template>

<style lang="css">
/* @import "assets/plugins/line-awesome/css/line-awesome.css"; */
</style>

<script>
import Comments from "./components/Comments.vue";
export default {
  name: "App",
  components: {
    Comments
  }
};
</script>