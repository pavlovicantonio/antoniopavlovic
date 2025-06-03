<script>
import MobileAppBar from './MobileAppBar.vue';
import MobileFooter from './MobileFooter.vue';

export default {
  data() {
    return {
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
      scrollPosition: 0,
      scrollSpeed: 1, // px po frame-u (možeš podesiti brzinu)
      animationFrameId: null,
    };
  },
  components: {
    MobileAppBar,
    MobileFooter
  },
  mounted() {
    // Nakon što se DOM učita, dupliciramo set slika
    const track = this.$refs.track;
    const originalSet = track.children[0];
    const clone = originalSet.cloneNode(true);
    track.appendChild(clone);

    // Pokreni scroll animaciju
    this.startScrolling();
  },
  beforeUnmount() {
    // Očisti animaciju kad komponenta nestane
    cancelAnimationFrame(this.animationFrameId);
  },
  methods: {
    startScrolling() {
      const track = this.$refs.track;
      const totalWidth = track.scrollWidth / 2; // polovica tracka jer imamo dva seta
      const step = () => {
        this.scrollPosition += this.scrollSpeed;
        if (this.scrollPosition >= totalWidth) {
          this.scrollPosition = 0; // reset scrolla na početak (glatko)
        }
        track.style.transform = `translateX(-${this.scrollPosition}px)`;
        this.animationFrameId = requestAnimationFrame(step);
      };
      this.animationFrameId = requestAnimationFrame(step);
    }
  }
};
</script>

<template>
  <v-sheet class="d-flex flex-column fill-height">
    <v-sheet id="firstVS_MS" class="flex-grow-1 d-flex flex-column">
      <MobileAppBar />
      <br /><br />
      <v-sheet
        class="d-flex align-center justify-center mt-16 flex-column"
        style="height: auto; background-color: transparent;"
      >
        <v-sheet
          class="d-flex flex-column"
          style="background-color: rgba(40, 44, 44, 0.7); height: auto; width: 90vw; border-radius: 10px; border: 1px solid #FF4500;"
        >
          <v-sheet
            class="d-flex"
            style="background-color: transparent; height: 10vh; width: 90vw;"
          >
            <h2
              class="d-flex align-center justify-center pl-5"
              style="font-family: 'Poppins', sans-serif; font-weight: bold; color: #FF4500; font-size: 2rem;"
            >
              My Dev Stack 💻
            </h2>
          </v-sheet>
          <v-sheet style="width: 90vw; height: auto; background-color: transparent;">
            <p
              class="pl-5 pr-5 mt-5"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE; font-size: 1.1rem;"
            >
              I build modern, responsive web applications using a clean and efficient tech stack. My current tools of
              choice include:
            </p>
            <p
              class="pl-5 pr-5 mt-4"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Vue 3 & Vuetify 3 – for building fast, interactive, and visually consistent user interfaces
            </p>
            <p
              class="pl-5 pr-5 mt-3"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              HTML5, CSS3, and JavaScript – the core technologies behind the structure, styling, and logic of the web
            </p>
            <p
              class="pl-5 pr-5 mt-3"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Firebase – for authentication, real-time databases, and scalable backend functionality
            </p>
            <p
              class="pl-5 pr-5 mt-3"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Node.js – to handle backend processes and server-side logic
            </p>
            <p
              class="pl-5 pr-5 mt-3"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Netlify – for reliable, fast, and easy deployment with built-in CI/CD support
            </p>
            <p
              class="pl-5 pr-5 mt-3"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Git & GitHub – for version control and collaborative development
            </p>
            <p
              class="pl-5 pr-5 mt-3 mb-5"
              style="text-align: justify; font-family: 'Poppins', sans-serif; color: #EEEEEE;"
            >
              Visual Studio Code – my preferred code editor, customized for productivity
            </p>
          </v-sheet>
        </v-sheet>
      </v-sheet>
    </v-sheet>

    <!-- Logo Slider Section -->
    <v-sheet id="secondVS_MS">
      <v-sheet class="d-flex align-center justify-center flex-column devstack-logos">
        <div ref="slider" class="logo-slider">
          <div ref="track" class="logo-track">
            <div class="logo-set">
              <img
                v-for="(logo, index) in logos"
                :key="index"
                :src="logo"
                class="logo-img"
                alt="Dev stack logo"
              />
            </div>
          </div>
        </div>
      </v-sheet>
    </v-sheet>

    <v-sheet id="thirdVS_MS">
      <MobileFooter />
    </v-sheet>
  </v-sheet>
</template>

<style>
#firstVS_MS {
  height: auto;
  width: 100vw;
  background-image: url('@/assets/template.svg');
}

#secondVS_MS {
  height: 50vh;
  width: 100vw;
  background-image: url('@/assets/template.svg');
  display: flex;
  flex-direction: column;
  justify-content: center;
}

#thirdVS_MS {
  background-image: url('@/assets/template.svg');
}

.devstack-logos {
  background-color: rgba(40, 44, 44, 0.9);
  min-height: 150px;
  width: 100vw;
  border-radius: 10px;
  padding: 1rem 0;
  overflow: hidden;
}

.logo-slider {
  overflow: hidden;
  width: 100%;
  position: relative;
}

.logo-track {
  display: flex;
  will-change: transform;
    animation: scrollLeft 30s linear infinite; /* povećaj po želji: 60s, 80s */

}

.logo-set {
  display: flex;
}

.logo-img {
  height: 15vh;
  margin-right: 3vw;
  object-fit: contain;
}
</style>
