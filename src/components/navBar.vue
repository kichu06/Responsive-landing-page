<template>
  <div class="logo" :class="{ active: isNavActive }">
    <img :src="logoSrc" alt="Bookmark logo" />
    <div class="nav-items" :class="{ active: isNavActive }">
      <a href="#">FEATURES</a>
      <a href="#">PRICING</a>
      <a href="#">CONTACT</a>
      <button class="btn-red">Login</button>
      <div class="social-media-logo mobile-btn">
        <img  src="../assets/images/icon-facebook.svg" alt="Facebook logo"/>
        <img  src="../assets/images/icon-twitter.svg" alt="twitter logo"/>
      </div>
    
    </div>

    <button
    class="mobile-btn"
    @click="mobileView"
    :aria-label="isNavActive ? 'Close navigation menu' : 'Open navigation menu'"
    :role="'button'"
  >
  <img
  :src="isNavActive ? require('@/assets/images/icon-close.svg') : require('@/assets/images/icon-hamburger.svg')"
  :alt="isNavActive ? 'Close button' : 'Hamburger button'"
/>
  </button>
  </div>
</template>

<script>
import logoDefault from '../assets/images/logo-bookmark.svg';
import logoActive from '../assets/images/logo-bookmark-white.svg';

export default {
  name: 'NavBar',
  data() {
    return {
      isNavActive: false
    };
  },
  methods: {
    mobileView() {
      this.isNavActive = !this.isNavActive;
    }
  },
  computed: {
    logoSrc() {
      return this.isNavActive ? logoActive : logoDefault;
    }
  }
};
</script>


<style lang="scss">
@import '../assets/navbar.scss';

</style>
