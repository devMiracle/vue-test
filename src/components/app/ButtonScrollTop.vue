<template>
  <div>
    <a
      @click="clickButtonTop"
      class="button-scroll-top btn-floating btn-large waves-effect waves-light red"
      ><i class="material-icons">arrow_upward</i></a
    >
  </div>
</template>
    

<script>
export default {
  methods: {
    clickButtonTop: () => {
      console.log("scroll");
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
.button-scroll-top {
  position: absolute;
  bottom: 15px;
  right: 15px;
  background: #ee6e73 !important;
  transition: .3s all ease-in-out;
  /* opacity: .8; */
  opacity: 0;
  /* display: none; */
}
.test {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0px;
}
.button-scroll-top-display{
  /* display: inline-block; */
  opacity: .8;
}
</style>
