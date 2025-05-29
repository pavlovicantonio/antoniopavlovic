<script>
import apwebing from "../../assets/apwebing3.png";
export default {
  data() {
    return {
      isFadingOut: false,
      isScrolled: false,
      isMenuOpen: false,
      currentIndex: 0,
      apwebing,
      wordList: ["Home", "About", "Projects", "Contact"], // ili bilo koje riječi želiš rotirati
      currentWord: "Home",
    };
  },
  mounted() {
    this.interval = setInterval(() => {
      this.startFadeOut();
    }, 3000);

    window.addEventListener("scroll", this.handleScroll);
  },
  watch: {
    isMenuOpen(val) {
      if (val) {
        document.body.style.overflow = "hidden";
        document.documentElement.style.overflow = "hidden";
      } else {
        document.body.style.overflow = "";
        document.documentElement.style.overflow = "";
      }
    },
  },
  beforeUnmount() {
    clearInterval(this.interval);
    window.removeEventListener("scroll", this.handleScroll);
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
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<template>
  <v-sheet
    id="first_SM"
    class="d-flex align-center"
    style="height: 8vh; z-index: 100"
  >
    <v-sheet
      :class="[{ scrolled: isScrolled }]"
      class="d-flex align-center justify-space-between px-4"
      style="width: 100vw; height: 8vh; background-color: transparent"
    >
      <v-img
        src="@/assets/apwebing3.png"
        class="d-flex align-center px-2"
        style="max-width: 120px; z-index: 100"
      ></v-img>

      <v-icon style="color: #ff4500" @click="toggleMenu()">
        {{ isMenuOpen ? "mdi-close" : "mdi-menu" }}
      </v-icon>
    </v-sheet>

    <v-sheet
      v-if="isMenuOpen"
      class="animate__animated animate__slideInRight"
      style="
        position: fixed;
        top: 8vh;
        left: 0;
        height: 92vh;
        width: 100vw;
        background-color: #1e1e1e;
        z-index: 9999;
      "
    >
      <div
        class="d-flex flex-column align-center justify-center"
        style="height: 100%"
      >
        <div class="menu-item">
          <router-link to="/" style="color: #eeeeee; text-decoration: none"
            >Home</router-link
          >
        </div>
        <div class="menu-item" @click="toggleMenu">Github</div>
        <div class="menu-item" @click="toggleMenu">Dev Stack</div>
        <div class="menu-item">
          <router-link
            to="/contact"
            style="color: #eeeeee; text-decoration: none"
            >Contact Us</router-link
          >
        </div>
      </div>
    </v-sheet>
  </v-sheet>
</template>

<style>
#first_SM {
  background-color: transparent;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
}
.menu-item {
  color: white;
  font-size: 2rem;
  margin: 20px 0;
  cursor: pointer;
  transition: color 0.3s;
}
.menu-item:hover {
  color: #ff4500;
}
</style>