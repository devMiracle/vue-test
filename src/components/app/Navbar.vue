<template>
  <div>
    <nav id="menu">
      <div class="nav-wrapper container style-nav">
        <router-link to="/" class="brand-logo">Logo</router-link>
        <router-link
          to="/"
          data-target="mobile-demo dropdown1"
          class="sidenav-trigger dropdown-trigger"
          ><i class="material-icons">menu</i></router-link
        >
        <ul id="nav-mobile" class="right hide-on-med-and-down">
          <router-link
            v-for="link in links"
            :key="link.url"
            :to="link.url"
            tag="li"
            active-class="active"
            :exact="link.exact"
          >
            <a href="#">{{ link.title }}</a>
          </router-link>
        </ul>
      </div>
    </nav>
    <div id="navbar-footer"></div>
    <!-- <ButtonScrollTop /> -->
  </div>

  
</template>

<script>
import "jquery/dist/jquery";
import ButtonScrollTop from '@/components/app/ButtonScrollTop'
export default {
  data: () => ({
    links: [
      { title: "home", url: "/", exact: true },
      { title: "about", url: "/about" },
      { title: "photo", url: "/1" },
      { title: "map", url: "/2" },
    ],
    num: 0,
  }),
  components: {
    ButtonScrollTop
  },
  methods: {
    scrollNavbar(event) {
      var wnd = window;
      var menu = document.getElementById("menu");
      var navbarFooter = document.getElementById("navbar-footer");

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
        navbarFooter.style.height = menu.scrollHeight + "px";
        menu.style.position = "fixed";
        menu.style.top = "0";
        //menu.style.left = "0";
        //menu.style.width = "100%";
      } else {
        menu.style = "";
        navbarFooter.style.height = "0px";
      }
    },
  },
  created() {
    window.addEventListener("scroll", this.scrollNavbar);
  },
  destroyed() {
    window.removeEventListener("scroll", this.scrollNavbar);
  },



  mounted() {
    // $(document).ready(function () {
    //   $(".sidenav").sidenav();
    // });
    // $('.dropdown-trigger').dropdown();
  },
};
</script>

<style scoped>
.style-nav {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.brand-logo {
  position: unset !important;
}
</style>