<template>
  <div class="preloader" v-if="preloader">
    <img src="/images/preloader.gif" alt>
  </div>
</template>
<script>
export default {
  computed: {
    preloader() {
      return this.$store.state.preloader.loading;
    }
  }
};
</script>
<style scoped>
.preloader {
  position: absolute;
  z-index: 9999;
  opacity: .6;
  width: 100%;
  height: 100%;
  margin: 0;
  text-align: center;
  padding: 10% 0;
}
.preloader img {
}
</style>