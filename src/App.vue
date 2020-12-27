<template>
  <div id="app">
    <div>
      <div class="container">
        <section id="head" class="section-head">
          <div class="container">
            <div class="d-flex justify-content-between p-2">
              <div class="d-flex flex-column justify-content-center">
                <div class="">+380980000000</div>
                <div class="">позвонить</div>
              </div>
              <div class="d-flex flex-column justify-content-center">
                <div class="title">Дратути )!)</div>
                <div class="sub-title">еше раз дратути</div>
              </div>
              <div class="d-flex flex-column justify-content-center">
                <div class="">qwerty@gmail.com</div>
                <div class="">mail</div>
              </div>
            </div>
          </div>
        </section>
      </div>

      <Navbar />
      <router-view class="container" />

      <div class="container test">
        <ButtonScrollTop />
      </div>

      <Footer />
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/app/Navbar";
import ButtonScrollTop from "@/components/app/ButtonScrollTop";
import Footer from "@/components/app/Footer";
export default {
  components: {
    Navbar,
    ButtonScrollTop,
    Footer,
  },
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.min.css";

// body {
//     display: flex !important;
//     min-height: 100vh !important;
//     flex-direction: column !important;
//   }

//   main {
//     flex: 1 0 auto !important;
//   }






html {
  scroll-behavior: smooth;
  overflow-y: scroll;
}

.test {
  position: fixed;

  left: 0;
  right: 0;
  bottom: 0px;
}
</style>
