<template>
  <section class="gallery">
    <img class="materialboxed" width="50" src="../images/img1.jpg">
  </section>
</template>


<script>
export default {
  mounted() {
    document.addEventListener('DOMContentLoaded', function() {
    var elems = document.querySelectorAll('.materialboxed');
    var instances = M.Materialbox.init(elems, { onOpenStart: () => console.log('click') });
  });
  }
  
}
</script>
