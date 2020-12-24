<template>
  <div id="app">
    <div>
      <div class="container">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Facilis magni
        commodi modi quo, aspernatur recusandae accusantium similique doloribus
        asperiores vero nobis placeat nihil deserunt, iusto sequi eum!
        Voluptates explicabo odio cum hic itaque? Eos ipsam ullam sapiente
        itaque, commodi doloribus maiores accusantium! Minus earum minima
        temporibus sint odio. Nulla at odio ipsa adipisci quidem laudantium
        itaque animi similique? Laudantium eveniet neque distinctio? Inventore
        ipsum nostrum similique non sequi praesentium consectetur veritatis
        perspiciatis minus animi aperiam cum pariatur accusamus accusantium
        tempora aliquam fugit eum, quas magni quos necessitatibus iste! Ullam
        iure ut rem consequatur incidunt ea enim nulla nihil obcaecati? Nulla
        facilis cumque asperiores delectus ipsum neque quam obcaecati tempora
        cupiditate quisquam voluptas reprehenderit sapiente inventore
        perferendis non ex cum a dolorem mollitia velit fuga, quibusdam
        officiis? Consequuntur fugiat odio ullam minima corrupti voluptatum esse
        impedit velit, vel est repellat ab ex exercitationem, accusantium id
        architecto magni tempora aspernatur pariatur, voluptatem ipsa voluptas
        error harum dolorem. Facilis numquam fugiat voluptates atque sunt, iure
        tempore neque? Quam quisquam laborum consectetur amet libero voluptates
        accusamus dolores vel, mollitia ipsa est cumque earum sed laudantium
        deleniti ut modi fugiat optio dicta at aliquam quis doloribus? Quasi
        iusto quod animi consequatur dolore ut error officia provident qui
        soluta saepe illum, ipsa quaerat assumenda fuga reiciendis fugit nemo
        inventore optio ea? Illo nihil officia debitis similique sequi ullam
        nemo! Fugit culpa porro ipsam! Rem facere, accusamus nobis explicabo cum
        ullam, quasi commodi ab aut libero atque mollitia eos odit, natus
        perferendis. Explicabo optio sint quos sunt deserunt facilis nostrum ad
        autem velit sequi, aspernatur molestias laborum, neque voluptate iusto
        veritatis quibusdam totam itaque numquam suscipit aperiam amet pariatur
        rem. Fugiat accusantium quam earum vero odio itaque est incidunt hic
        perferendis distinctio, totam dolores facilis, expedita, illo sed quasi
        enim. Odit, ipsa explicabo? Repudiandae ullam ipsum est?
      </div>

      <Navbar />
      <router-view class="container" />
    </div>
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
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.css";

html {
  scroll-behavior: smooth;
  overflow-y: scroll;
}
</style>
