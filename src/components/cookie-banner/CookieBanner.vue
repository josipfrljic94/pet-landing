<template>
  <div v-if="!isCookieAccepted" class="cookie-banner">
    <p>{{ message }}</p>
    <button @click="acceptCookies">Accept</button>
  </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      isCookieAccepted: false,
      message: "This website uses cookies to enhance your experience.",
    };
  },
  mounted() {
    const accessAllow = this.getCookie('access-allow');
    if (accessAllow === 'true') {
      this.isCookieAccepted = true;
    }
  },
  methods: {
    acceptCookies() {
      this.setCookie('access-allow', 'true', 365);
      this.isCookieAccepted = true;
    },
    setCookie(name, value, days) {
      const expires = new Date();
      expires.setDate(expires.getDate() + days);
      document.cookie = `${name}=${value};expires=${expires.toUTCString()};path=/`;
    },
    getCookie(name) {
      const value = `; ${document.cookie}`;
      const parts = value.split(`; ${name}=`);
      if (parts.length === 2) return parts.pop().split(';').shift();
    },
  },
});
</script>
  
<style scoped>
.cookie-banner {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: #666666;
  color: white;
  padding: 10px;
  text-align: center;

  &>button {
    appearance: none;
    border: none;
    height: 30px;
    width: 120px;
    padding: 0 10px;
    cursor: pointer;
    background-color: #e8e7e7;
    &:hover{
      background-color: #fafafa;
    }
  }
}
</style>
  