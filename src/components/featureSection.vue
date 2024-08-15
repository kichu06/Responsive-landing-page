<template>
  
    <div class="feature-container">
        <div class="feature-section">
              <h1>Features</h1>
              <p>
                Our aim is to make it quick and easy for you to access your favourite websites. Your bookmarks sync between your devices so you can access them on the go.
              </p>
              <div class="feature-links">
                <a href="#"  ref="defaultFocus" class="feature-link" @click.prevent="showFeature('bookmarking')">Simple Bookmarking</a>
                <a href="#" class="feature-link" @click.prevent="showFeature('searching')">Speedy Searching</a>
                <a href="#" class="feature-link" @click.prevent="showFeature('sharing')">Easy Sharing</a>
              </div>
            </div>
      </div>


            <div v-if="currentFeature === 'bookmarking'" class="feature-details">
              <div class="image-container"> <img src="../assets/images/illustration-features-tab-1.svg" alt="Bookmark Banner"/></div>
              <div class="content-details">
                <h1>Bookmark in one click</h1>
                <p>Organize your bookmarks however you like. Our simple drag-and-drop interface gives you complete control over how you manage your favourite sites.</p>
                <button class="btn-blue" >More Info</button > 
              </div> 
            </div>


            <div v-if="currentFeature === 'searching'" class="feature-details">
              <div class="image-container"> <img src="../assets/images/illustration-features-tab-2.svg" alt="Search Banner"/></div>
              <div class="content-details">
              <h1>Speedy Searching</h1>
              <p>ur powerful search feature will help you find saved sites in no time at all. No need to trawl through all of your bookmarks.</p>
              <button class="btn-blue" >More Info</button>
              </div>
            </div>

              
              <div v-if="currentFeature === 'sharing'" class="feature-details">
                <div class="image-container"> <img src="../assets/images/illustration-features-tab-3.svg" alt="Share Banner"/>
                </div>
                <div class="content-details">
                  <h1>Share your bookmarks</h1>
                <p>Easily share your bookmarks and collections with others. Create a shareable link that you can send at the click of a button.</p>
                <button class="btn-blue">More Info</button>
                </div> 
             </div> 

</template>

<script>
export default {
  data() {
    return {
      currentFeature: "bookmarking"
    };
  },
  mounted() {
   
    this.$refs.defaultFocus.focus();
  },
  methods: {
    showFeature(feature) {
      console.log('clicked')
      this.currentFeature = feature;
    }
  }
};
</script>

<style lang="scss">
@import '../assets/featureSection.scss'
</style>