<template>
<headerPage></headerPage>
  <timeline></timeline>
  <team></team>
  <faq></faq>
</template>

<script>
import headerPage from "./components/headerPage";
import timeline from "./components/timeline";
import team from "./components/team";
import faq from "./components/faq";
import 'aos/dist/aos.css'
import AOS from "aos";

export default {
  name: 'App',
  components: {
    headerPage,
    timeline,
    team,
    faq,
  },
  mounted() {
    AOS.init({disable: 'mobile'});
  }

}
</script>

<style>
@import "../public/kango-retro-font/Kango/Web-TT/Kango Typeface.css";
@font-face {
  font-family: 'Metropolis';
  src: local('Metropolis'),
  url('../public/metropolis/Metropolis-Regular.otf') format('opentype');
}
</style>
