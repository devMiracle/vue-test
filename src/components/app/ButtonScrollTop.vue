<template>
  <!-- <div class="container test"> -->
  <div>
    <a
      href="#app"
      @click.prevent="clickButtonTop"
      class="button-scroll-top btn-floating btn-large waves-effect waves-light red"
      ><i class="material-icons">arrow_upward</i></a
    >
  </div>
</template>
    

<script>
export default {
  methods: {
    clickButtonTop: () => {},
  },
};
</script>

<style scoped>
.button-scroll-top {
  position: absolute;
  bottom: 15px;
  right: 15px;
  background: #ee6e73 !important;
}
.test {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0px;
  
}
</style>
