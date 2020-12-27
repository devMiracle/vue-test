<template>
  <section class="home">
    <div class="section white">
      <div class="row container">
        <h2 class="header">Parallax</h2>
        <p class="grey-text text-darken-3 lighten-3">
          Parallax is an effect where the background content or image in this
          case, is moved at a different speed than the foreground content while
          scrolling.
        </p>
      </div>
    </div>
    <div class="parallax-container">
      <div class="parallax">
        <img src="../images/back-cake.jpg" alt="image" />
      </div>
    </div>
    <div class="section white">
      <div class="row container">
        <h2 class="header">Parallax</h2>
        <p class="grey-text text-darken-3 lighten-3">
          Parallax is an effect where the background content or image in this
          case, is moved at a different speed than the foreground content while
          scrolling.
        </p>
      </div>
    </div>
    <div class="parallax-container">
      <div class="parallax">
        <img src="../images/back-cake2.jpg" alt="image" />
      </div>
    </div>

     

    
  </section>
</template>

<style scoped>
</style>

<script>
export default {
  
  created() {
document.addEventListener("DOMContentLoaded", function () {
      var elems = document.querySelectorAll(".parallax");
      var instances = M.Parallax.init(elems);
    });
  },
  beforeCreate() {
// document.addEventListener("DOMContentLoaded", function () {
//       var elems = document.querySelectorAll(".parallax");
//       var instances = M.Parallax.init(elems);
//     });
  },
  beforeMount() {
    // document.addEventListener("DOMContentLoaded", function () {
    //   var elems = document.querySelectorAll(".parallax");
    //   var instances = M.Parallax.init(elems);
    // });
  },
  mounted() {
    // document.addEventListener("DOMContentLoaded", function () {
    //   var elems = document.querySelectorAll(".parallax");
    //   var instances = M.Parallax.init(elems);
    // });
  },
};
</script>

