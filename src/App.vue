<template>
  <div>
    <header>
      <navBar />
    </header>
    <main>
      <mainSection />
      <featureSection />
      <exTension/>
      <AcCordian/>
      <contactUs/>
    </main>
    <footer>
      <footerBar/>
    </footer>
  </div>
</template>

<script>
import navBar from './components/navBar.vue'
import mainSection from './components/mainSection.vue'
import featureSection from './components/featureSection.vue';
import exTension from './components/exTension.vue';
import AcCordian from './components/acCordian.vue';
import contactUs from './components/contactUs.vue';
import footerBar from './components/footerBar.vue';
export default {
  name: 'App',
  components: {
    navBar,
    mainSection,
    featureSection,
    exTension,
    AcCordian,
    contactUs,
    footerBar
  }
}
</script>

<style lang="scss">
@import './assets/style.scss';

</style>
