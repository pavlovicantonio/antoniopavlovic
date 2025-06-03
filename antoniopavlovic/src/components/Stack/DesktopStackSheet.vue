<script>
import { useRoute } from 'vue-router'

export default {
  data() {
    return {
      wordList: ['FAST', 'MODERN', 'RESPONSIVE', 'CREATIVE'],
      currentIndex: 0,
      currentWord: 'FAST',
      isFadingOut: false,
      isScrolled: false
    };
  },
  mounted() {
    this.interval = setInterval(() => {
      this.startFadeOut();
    }, 3000);

    window.addEventListener('scroll', this.handleScroll);
  },
  setup(){
    const route = useRoute();
    return { route };
  },
  beforeUnmount() {
    clearInterval(this.interval);
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    startFadeOut() {
      this.isFadingOut = true;

      setTimeout(() => {
        this.currentIndex = (this.currentIndex + 1) % this.wordList.length;
        this.currentWord = this.wordList[this.currentIndex];
        this.isFadingOut = false;
      }, 700);
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 0;
    }
  }
};
</script>

<template>
    <v-sheet id="vs_DSD" style="height: 100vh; width: 100vw;" class="d-flex flex-column">
<v-sheet class="mainV_Sheet d-flex flex-column" style="height: 100%;">
    <v-sheet :class="['custom-app-bar', { 'scrolled': isScrolled }]" class="d-flex align-center px-4">
      <a
        href="https://apwebing.netlify.app"
        target="_blank"
        rel="noopener"
        style="display: block; width: 300px;"
      ><v-img
        src="@/assets/apwebing3.png"
        alt="Logo"
        height="55"
        style="max-width: 180px;"
      ></v-img></a>

      <v-spacer></v-spacer>

      <span>
      <router-link to="/" class="btn-link" :style="{ color: route.path === '/' ? '#FF4500' : '#EEEEEE' }">HOME</router-link>
      <a href="https://github.com/pavlovicantonio" target="_blank" class="btn-link">GITHUB</a>
      <router-link to="/stack" class="btn-link" :style="{ color: route.path === '/stack' ? '#FF4500' : '#EEEEEE'}">DEV STACK</router-link>
    </span>
      
    </v-sheet>
<v-sheet class="d-flex align-center justify-center flex-column" style="height: 100vh; background-color: transparent; color: #FF4500;">
  <h1 style="font-family: 'Poppins', sans-serif; font-size: 4rem;">COOMING SOON!</h1>
</v-sheet>
    </v-sheet>
      
    </v-sheet>
</template>

<style>
#vs_DSD{
  background-image: url('@/assets/template.svg');
}
</style>