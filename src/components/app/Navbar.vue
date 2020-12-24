<template>
  <div>
    <nav id="menu">
      <div class="nav-wrapper">
        <router-link to="/" class="brand-logo">Logo</router-link>
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
export default {
  data: () => ({
    links: [
      { title: "home", url: "/", exact: true },
      { title: "about", url: "/about" },
      { title: "photo", url: "/1" },
      { title: "map", url: "/2" },
    ],
  }),
};
</script>