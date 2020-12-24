<template>
  <div id="app">
    <span>
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
      111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
</span>

    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "@/components/app/Navbar";
export default {
  components: {
    Navbar,
  },
  data: () => ({
    num: 0,
  }),
  methods: {
    scrollNavbar(event) {
      var wnd = window;
      var menu = document.getElementById("menu");
      var navbarFooter = document.getElementById("navbar-footer")

      // console.log("num: " + this.num);
      // console.log("1: " + wnd.scrollY);
      // console.log("2: " + menu.offsetTop);

      // console.log({menu});
      // console.log(menu.clientHeight);
      // console.log(menu.offsetHeight);
      // console.log(menu.scrollHeight);

      // console.log(navbarFooter.style.height);

      if (menu.offsetTop != 0) {
        this.num = menu.offsetTop;
      }
      if (wnd.scrollY >= this.num) {
        navbarFooter.style.height = menu.scrollHeight + 'px'
        menu.style.position = "fixed";
        menu.style.top = "0";
        //menu.style.left = "0";
        //menu.style.width = "100%";
      } else {
        menu.style = "";
        navbarFooter.style.height = '0px'
      }
    },
  },
  created() {
    window.addEventListener("scroll", this.scrollNavbar);
  },
  destroyed() {
    window.removeEventListener("scroll", this.scrollNavbar);
  },
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.min.css";
</style>
