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
  setup(){
    const route = useRoute();
    return { route };
  },
  mounted() {
    this.interval = setInterval(() => {
      this.startFadeOut();
    }, 3000);

    window.addEventListener('scroll', this.handleScroll);
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
  <v-sheet class="mainV_Sheet">
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

    <v-sheet class="secondV_Sheet d-flex align-center justify-center">
      <div class="headline-wrapper" style="padding: 100px;">
          <div class="word" style="cursor: default;">CRAFT</div>
          <div class="word" style="cursor: default;">YOUR</div>
          <div class="word highlight" style="cursor: default;">ONLINE</div>
          <div class="word" style="cursor: default;">FUTURE</div>
        </div>
    </v-sheet>

    <v-sheet class="thirdV_Sheet">
      <div>
        <div class="word2" style="color: #EEEEEE; cursor:default">WE BUILD<span :class="['animated-word','animate__animated',isFadingOut ? 'animate__fadeOutUp' : 'animate__fadeInUp']" style="color: #FF4500; cursor: default;" :key="currentWord">
          {{ currentWord }}</span>
        </div>   
      </div>
    </v-sheet>
  </v-sheet>
</template>

<style>
.btn-link {
  color: #EEEEEE;
  background-color: transparent;
  text-decoration: none;
  margin: 0 8px;
  padding: 6px 12px;
  font-weight: bold;
  transition: 0.3s ease;
}

.btn-link:hover {
  color: #FF4500;
}
.mainV_Sheet{
  height: 100%;
  width: 100vw;
  background-image: url('../assets/template.svg');
  background-size: cover;
  background-position: center;
  display: flex;
}
.custom-app-bar{
  background-color: transparent !important; 
  box-shadow: none !important;
  position: fixed;
  top: 0px;
  left: 0px;
  right: 0px;
  height: 15vh;
}
.scrolled {
  background-color: #282c2c !important;
  transition: background-color 0.3s ease;
  z-index: 10;
}
.secondV_Sheet{
  height: 90vh;
  width: 50vw;
  display: flex;
  background-color: transparent;
  margin-top: 10vh;
}
.thirdV_Sheet{
  height: 90vh;
  width: 50vw;
  display: flex;
  background-color: transparent;
  margin-top: 10vh;
}
.headline-wrapper {
  display: flex;
  flex-direction: column;
  align-items: left;
  text-align: left;
  gap: 8px;
}
.word {
  font-family: 'Poppins', sans-serif;
  font-size: 5rem;
  font-weight: bolder;
  letter-spacing: 10px;
  color: #EEEEEE;
}
.word:hover {
  color: #FF4500;
}

.highlight {
  color: #FF4500;
}

.highlight:hover {
  color: #EEEEEE;
}
.word2{
  position: relative;
  top: 60vh;
  left: 5vw;
  font-family: 'Anton', sans-serif;
  font-size: 3rem;
  display: flex;
}
/* Animacija za fadeOutUp i fadeInUp */
.fade-up-transition-enter-active, .fade-up-transition-leave-active {
  transition: all 1.5s ease;
  display: inline-block;
}

.fade-up-transition-enter {
  opacity: 0;
  transform: translateY(100%);
}

.fade-up-transition-leave-to {
  opacity: 0;
  transform: translateY(-100%);
}

.animated-word {
  margin-left: 10px;
  display: inline-block;
}

.animate__fadeOutUp {
  animation: fadeOutUp 1.5s forwards;
}

.animate__fadeInUp {
  animation: fadeInUp 1.5s forwards;
}

/* Definiramo animacije pomoću keyframes */
@keyframes fadeOutUp {
  0% {
    opacity: 1;
    transform: translateY(0);
  }
  100% {
    opacity: 0;
    transform: translateY(-100%);
  }
}

@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>