<script>
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
    <v-sheet>
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

      <v-btn variant="text" to="/" class="btn" color="#EEEEEE">HOME</v-btn>
      <v-btn variant="text" class="btn" color="#EEEEEE">GITHUB</v-btn>
      <v-btn variant="text" to="stack" class="btn" color="#EEEEEE">DEV STACK</v-btn>
      
    </v-sheet>

        <v-sheet class="DSS1">

        </v-sheet>
    
        </v-sheet>
    </v-sheet>
</template>