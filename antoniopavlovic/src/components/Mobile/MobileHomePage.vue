<script>
import MobileAppBar from './MobileAppBar.vue';

export default {
  components: {
    MobileAppBar
  },
  data() {
    return {
      wordList: ['FAST', 'MODERN', 'RESPONSIVE', 'CREATIVE'], // možeš prilagoditi riječi
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
}
</script>

<template>
<v-sheet style="position: relative; z-index: 0;">

    <v-sheet id="secondVS_MHP" style="height: 100vh; width: 100vw;">
      <MobileAppBar />
      <v-sheet class="headline-wrapperMobile d-flex align-center justify-center" style="height: 92vh; width: 100vw; display: flex; background-color: transparent;">
        <v-sheet style="text-align: left; background-color: transparent;">
            <div class="wordMobile">CRAFT</div>
            <div class="wordMobile">YOUR</div>
            <div class="wordMobile highlight">ONLINE</div>
            <div class="wordMobile">FUTURE</div>
        </v-sheet>

        <div class="we-build-wrapper" style="margin-top: 40px;">
            <div class="we-build-text">WE BUILD</div>
            <div :class="['rotating-word','wordMobile','animate__animated',isFadingOut ? 'animate__fadeOutUp' : 'animate__fadeInUp']">{{ currentWord }}</div>
        </div>
      </v-sheet>
    </v-sheet>

    <v-sheet id="thirdVS_MHP" class="d-flex align-center justify-center" style="height: 100vh; width: 100vw;">
        
        <v-sheet style="background-color: rgba(40, 44, 44, 0.7); height: 90vh; width: 90vw; border-radius: 10px;"  class="d-flex flex-column align-center justify-center">
            <p class="our-work-mobile">Our <span style="color: #FF4500;">work</span></p>
            <p class="our-work-mobile" style="color: #CCCCCC; font-weight: normal; font-size: 1.5rem; margin-bottom: 1vh;">Crafting web and mobile apps</p>
            <v-sheet style="height: 75vh; width: 85vw; border: 1px solid #FF4500; background-color: transparent; margin-bottom: 2vh; border-radius: 10px;">
                <v-sheet style="width: 85vw; height: 8.5vh; background-color: transparent;" class="d-flex align-center justify-start">
                      <h2 class="ml-3" style="font-size: 1.8rem; color: #FF4500; margin: 0; font-family: 'Poppins', sans-serif; font-weight: bold;">Technologies I Use</h2>
                </v-sheet>
                <v-sheet style="width: 85vw; height: 23vh; background-color: transparent;">
                    <v-img src="../../assets/pc.png"></v-img>
                </v-sheet>
                <v-sheet style="width: 85vw; height: 43vh; background-color: transparent;">
                    <p class="tech-i-use-text">As a computer science student with a strong passion for web development, I constantly strive to learn and improve. Every project is an opportunity for me to grow, and I give my full dedication to creating thoughtful, user-friendly websites. I primarily work with modern technologies like Vue.js and Vuetify to build clean, responsive interfaces.</p>
                </v-sheet>
            </v-sheet>
        </v-sheet>
    </v-sheet>



    <v-sheet id="thirdVS_MHP" class="d-flex align-center justify-center" style="height: 100vh; width: 100vw;">
        <v-sheet style="background-color: rgba(40, 44, 44, 0.7); height: 90vh; width: 90vw; border-radius: 10px;"  class="d-flex flex-column align-center justify-center">
            <v-sheet style="height: 75vh; width: 85vw; border: 1px solid #FF4500; background-color: transparent; margin-bottom: 2vh; border-radius: 10px;">
                <v-sheet style="width: 85vw; height: 8.5vh; background-color: transparent;" class="d-flex align-center justify-start">
                      <h2 class="ml-3" style="font-size: 1.8rem; color: #FF4500; margin: 0; font-family: 'Poppins', sans-serif; font-weight: bold;">Web & App Dev</h2>
                </v-sheet>
                <v-sheet style="width: 85vw; height: 23vh; background-color: transparent;">
                    <v-img src="../../assets/mokcups.png"></v-img>
                </v-sheet>
                <v-sheet style="width: 85vw; height: 43vh; background-color: transparent;">
                    <p class="tech-i-use-text">I specialize in building modern, responsive websites and mobile-friendly interfaces that not only look great but also provide a smooth user experience across all devices. Whether it's a personal portfolio, a business presentation, or a full-featured web application, my goal is to craft clean and efficient solutions tailored to the needs of each project.</p>
                </v-sheet>
            </v-sheet>
        </v-sheet>
    </v-sheet>



  </v-sheet>
</template>

<style>
#secondVS_MHP {
  background-image: url('@/assets/template.svg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
 .headline-wrapperMobile {
    display: flex;
  flex-direction: column;
  align-items: flex-start; /* lijevo poravnanje elemenata unutar wrappera */
  text-align: left;        /* lijevo poravnjanje teksta */
  padding: 10px 20px;
  max-width: 600px;        /* npr. širina teksta, možeš prilagoditi */
  margin: 0 auto;          
  }

  .wordMobile {
    font-family: 'Anton', sans-serif;
    font-size: 3.5rem;
    letter-spacing: 6px;
    color: #EEEEEE;
  }
  .wordMobile:hover{
    color:#FF4500;
  }
  .highlight{
    color: #FF4500;
  }
  .highlight:hover{
    color: #EEEEEE;
  }
  .we-build-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center; /* lijevo poravnanje */
  text-align: left;
  width: 100vw;
  font-family: 'Anton', sans-serif;
    font-size: 2rem;
    letter-spacing: 3px;
}

.we-build-text {
  margin-bottom: 10px;
  letter-spacing: 6px;
  color: #EEEEEE;
}

.rotating-word {
  font-size: 2rem;
  color: #FF4500;
  transition: opacity 0.7s ease;
  position: relative;
  z-index: 0;
}

#thirdVS_MHP{
  background-image: url('@/assets/template.svg');
}

.our-work-mobile{
    font-size: 2rem;
    color: #EEEEEE;
    width: 85vw;
    font-family: 'Poppins', sans-serif;
    font-weight: bold;
    margin: 0;
  padding: 0;
  line-height: 1.2;
}
.tech-i-use-text {
  font-size: clamp(1rem, 2.5vw, 2rem); /* raste s ekranom */
  padding: 2vh 4vw;
  text-align: justify;
  line-height: 1.6;
  color: #EEEEEE;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  font-family: 'Poppins', sans-serif;
}
</style>
