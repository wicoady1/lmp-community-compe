<template>
  <div id="app">
    <header-section></header-section>
    <intro-section></intro-section>
    <sdvx-section></sdvx-section>
    <iidx-section></iidx-section>
    <ddr-section></ddr-section>
    <footer-section></footer-section>
  </div>
</template>

<script>
import HeaderSection from './components/HeaderSection.vue'
import IntroSection from './components/IntroSection.vue'
import SDVXSection from './components/1SDVXSection.vue'
import IIDXSection from './components/2IIDXSection.vue'
import DDRSection from './components/3DDRSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'app',
  components: {
    'header-section': HeaderSection,
    'intro-section': IntroSection,
    'sdvx-section': SDVXSection,
    'iidx-section': IIDXSection,
    'ddr-section': DDRSection,
    'footer-section': FooterSection
  }
}
</script>

<style>
html {
  scroll-behavior: smooth;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body{
  margin: 0 0 0 0;
  font-family: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
}
</style>
