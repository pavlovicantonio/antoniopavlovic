<script>
import { useRoute } from 'vue-router'
import DesktopHomeFooter from '../DesktopHomeFooter.vue'

export default {
  data() {
    return {
      wordList: ['FAST', 'MODERN', 'RESPONSIVE', 'CREATIVE'],
      currentIndex: 0,
      currentWord: 'FAST',
      isFadingOut: false,
      isScrolled: false,
      logos: [
        new URL('@/assets/html.png', import.meta.url).href,
        new URL('@/assets/css.png', import.meta.url).href,
        new URL('@/assets/javascript.png', import.meta.url).href,
        new URL('@/assets/github.png', import.meta.url).href,
        new URL('@/assets/git.png', import.meta.url).href,
        new URL('@/assets/document.png', import.meta.url).href,
        new URL('@/assets/logo.svg', import.meta.url).href,
        new URL('@/assets/nodejs.png', import.meta.url).href,
        new URL('@/assets/firebase.png', import.meta.url).href,
        new URL('@/assets/visual-studio.png', import.meta.url).href,
        new URL('@/assets/netlif.png', import.meta.url).href,
      ],

    };
  },
  components:{
    DesktopHomeFooter
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
    <v-sheet id="vs_DSD" style="height: 130vh;  width: 100vw;" class="d-flex flex-column">
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
  <v-container class="mt-12">
  <v-row>
    <v-col cols="12" md="6">
      <h2 class="text-orange-500 text-3xl font-bold mb-4" style="font-family: 'Poppins', sans-serif;">My Dev Stack 💻</h2>
      <p class="text-white text-lg mb-4" style="font-family: 'Poppins', sans-serif;">
        I build modern, responsive web applications using a clean and efficient tech stack. My tools of choice include:
      </p>
      <ul class="text-white text-base" style="font-family: 'Poppins', sans-serif;">
        <li><strong class="text-orange-500">Vue 3 & Vuetify 3:</strong> for fast, interactive UIs</li>
        <li><strong class="text-orange-500">HTML5, CSS3, JavaScript:</strong> core web technologies</li>
        <li><strong class="text-orange-500">Firebase:</strong> real-time DB & auth</li>
        <li><strong class="text-orange-500">Node.js:</strong> server-side logic</li>
        <li><strong class="text-orange-500">Netlify:</strong> deployment with CI/CD</li>
        <li><strong class="text-orange-500">Git & GitHub:</strong> version control</li>
        <li><strong class="text-orange-500">VS Code:</strong> preferred editor</li>
      </ul>
    </v-col>

    <v-col cols="12" md="6" class="d-flex align-center justify-center">
      <v-img src="@/assets/guy1.png" max-width="300" class="rounded-xl" />
    </v-col>
  </v-row>

  <v-divider class="my-8" />

  <!-- Logo slider -->
  <v-sheet class="logo-slider-container">
    <div class="logo-track-desktop">
      <div class="logo-set">
        <img
          v-for="(logo, index) in logos"
          :key="index"
          :src="logo"
          class="logo-img"
          alt="tech logo"
        />
      </div>
    </div>
  </v-sheet>
</v-container>

</v-sheet>
 <DesktopHomeFooter/> 
    </v-sheet>
      
    </v-sheet>
</template>

<style>
#vs_DSD{
  background-image: url('@/assets/template.svg');
}
.logo-slider-container {
  overflow: hidden;
  background-color: rgba(40, 44, 44, 0.9);
  border-radius: 10px;
  padding: 1rem 0;
  width: 100%;
}

.logo-track-desktop {
  display: flex;
  animation: scrollLeft 40s linear infinite;
  will-change: transform;
}

.logo-img {
  height: 80px;
  margin: 0 2rem;
  object-fit: contain;
}

@keyframes scrollLeft {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

</style>