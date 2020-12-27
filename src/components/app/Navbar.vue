<template>
  <div>
    <nav id="menu">
      <div class="nav-wrapper container style-nav">
        <router-link to="/" class="brand-logo">
         <div class="logo-container">
            <img class="logo" src="@/assets/muffin-logo.jpg" alt="muffin" />
         </div>
        </router-link>
        <!-- <a href="#" data-activates="mobile-demo" class="button-collapse">
          <i class="material-icons">menu</i>
        </a> -->
        <!-- <router-link
          to="/"
          data-target="mobile-demo dropdown1"
          class="sidenav-trigger dropdown-trigger"
        >
          <i class="material-icons">menu</i>
        </router-link> -->
        <a href="#" data-target="mobile-demo" class="right sidenav-trigger"
          ><i class="material-icons">menu</i></a
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

    <ul class="sidenav" id="mobile-demo" @click="closeSidenav">
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

    <div id="navbar-footer"></div>
    <!-- <ButtonScrollTop /> -->
  </div>
</template>

<script>
import { JQuery, $ } from "jquery";
import ButtonScrollTop from "@/components/app/ButtonScrollTop";
export default {
  data: () => ({
    links: [
      { title: "Главная", url: "/", exact: true },
      { title: "Галерея", url: "/gallery" },
      { title: "Начинки", url: "/1" },
      { title: "Доставка", url: "/2" },
      { title: "Обратная связь", url: "/3" },
      { title: "Начинки", url: "/4" },
    ],
    num: 0,
  }),
  components: {
    ButtonScrollTop,
  },
  methods: {
    closeSidenav: () => {
      var elem = document.getElementById("mobile-demo");
      var instance = M.Sidenav.getInstance(elem);
      instance.close();
    },

    scrollNavbar(event) {
      var wnd = window;
      var menu = document.getElementById("menu");
      var navbarFooter = document.getElementById("navbar-footer");
      var ButtonScrollTop = document.querySelector(".button-scroll-top");
      // console.log(ButtonScrollTop)
      if (menu.offsetTop != 0) {
        this.num = menu.offsetTop;
      }
      if (wnd.scrollY >= this.num) {
        navbarFooter.style.height = menu.scrollHeight + "px";
        menu.style.position = "fixed";
        menu.style.top = "0";
        //menu.style.left = "0";
        //menu.style.width = "100%";
        ButtonScrollTop.classList.add("button-scroll-top-display");
      } else {
        menu.style = "";
        navbarFooter.style.height = "0px";
        ButtonScrollTop.classList.remove("button-scroll-top-display");
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
    document.addEventListener("DOMContentLoaded", function () {
      var elems = document.querySelectorAll(".sidenav");
      var instances = M.Sidenav.init(elems, {
        edge: "left",
        draggable: true,
        inDuration: 250,
        outDuration: 250,
      });
    });
  },
};
</script>

<style scoped>
/* .style-nav {
  display: flex;
  justify-content: space-around;
} */
/* .brand-logo {
  position: inherit;
} */
.sidenav {
  width: auto;
  height: auto;
  border-radius: 0 0 15px 0;
  padding-bottom: 0;
  opacity: 0.85;
}
.logo-container {
  width: 64px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 30px;
  
}
  @media screen and (max-width: 992px) {
    .logo-container {
      margin-left: 0;
    }
  }


.logo {
  display: flex;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  transform: scale(1.6);
  border: 3px dotted #ee6e73;
}
</style>