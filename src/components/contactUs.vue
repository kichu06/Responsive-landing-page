<template>
  <div class="contact-container">
    <div class="contact-content">
      <p>35,000+ already joined</p>
      <h1>Stay up-to-date with what we’re doing</h1>
      <div class="input-container">
        <div class="input-field-container">
          <input 
          @focus="clearError"
          type="email" 
          v-model="email"  
          :class="{'input-error': errorMessage}"
           placeholder="Enter your email address">
          <img src="../assets/images/icon-error.svg"  v-if="errorMessage" class="error-logo" alt="'error logo"/>
          <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
        </div>
        <button class="btn-red" @click="handleSubmit">Contact Us</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data(){
      return{
        email:'',
         errorMessage: ''
      }
    },
    methods:{
      handleSubmit(){
          const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
          if (!emailPattern.test(this.email)) {
            this.errorMessage = `Whoops, make sure it's an email`;
          } else {
            this.errorMessage = '';
            this.email='';
            console.log('Valid email:', this.email);
         }
      },
      clearError() {
      this.errorMessage = '';
    }
    }
}
</script>

<style lang="scss">
@import '../assets/contactUs.scss';

</style>