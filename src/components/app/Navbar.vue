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
  </div>

  
</template>

<script>
import "jquery/dist/jquery";
export default {
  data: () => ({
    links: [
      { title: "home", url: "/", exact: true },
      { title: "about", url: "/about" },
      { title: "photo", url: "/1" },
      { title: "map", url: "/2" },
    ],
  }),
  methods: {},
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