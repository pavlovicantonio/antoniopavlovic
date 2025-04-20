<template>
  <v-sheet v-if="mobile" class="background">
    <v-sheet id="topBar" class="pa-4 d-flex align-center justify-space-between">
      <div class="d-flex align-center">
        <h1 v-show="!menuOpen" class="topBarH1 animate__animated animate__fadeInDown">
          Antonio Pavlović
        </h1>

        <div v-if="menuOpen" class="ml-4 d-flex align-center nav-links animate__animated animate__fadeInLeft">
          <span class="nav-link">CONTACT</span>
          <span class="nav-link">ABOUT ME</span>
          <span class="nav-link">MY WORK</span>
        </div>
      </div>
      <v-icon class="topBarMenuIcon animate__animated animate__backInRight animate__delay-0.5s" style="color: #EEEEEE" @click="toggleMenu">
        {{ menuOpen ? 'mdi-close' : 'mdi-menu' }}
      </v-icon>
    </v-sheet>

    <!-- First Section -->
    <div ref="firstRef">
      <v-sheet v-show="showFirst" class="firstSheet">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          Why did I make my own website?
        </h3><br>
        <p class="animate__animated animate__zoomIn" style="font-family: 'Inter', sans-serif !important;">
          It all began when I dove into studying and started building websites. Before long, a few friends asked me to create sites for them, they liked my style and approach. That sparked an idea: why not build my own personal website? A place where I can share a bit about who I am and leave a form for anyone who's dreaming of having their own custom site. If that's you, let's make it happen.
        </p>
      </v-sheet>
    </div>

    <!-- Second Section -->
    <div ref="secondRef">
      <v-sheet v-show="showSecond" class="secondSheet">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          Looking for your own website?
        </h3><br>
        <p class="animate__animated animate__slideInLeft" style="font-family: 'Inter', sans-serif !important;">
          In today’s digital world, having a professional website is a must. Whether you are an individual or a business, a good website can be your best marketing tool, your online portfolio, or even your shopfront.
        </p><br>
        <p class="animate__animated animate__slideInRight" style="font-family: 'Inter', sans-serif !important;">
          Let’s build a website that not only looks amazing but also functions seamlessly. I aim to create websites that not only showcase your brand or product but also deliver the best user experience.
        </p>
      </v-sheet>
    </div>

    <!-- Third Section -->
    <div ref="thirdRef">
      <v-sheet v-show="showThird" class="thirdSheet animate__animated animate__fadeInUp animate__slower">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          My products
        </h3><br>
        <center>
          <v-img src="../assets/programmer.gif" style="width: 30%; display: inline-block"></v-img>
          <v-img src="../assets/arrow.gif" style="width: 30%; display: inline-block;"></v-img>
          <v-img src="../assets/product.gif" style="width: 30%; display: inline-block;"></v-img>
        </center> 
        <br>
        <p>Here are some of the websites I’ve built so far. From simple landing pages to complex, multi-page websites, each project reflects a unique vision and a strong attention to detail.</p><br>
        <p>Each project reflects a unique vision, custom-tailored to fit the client's needs. Whether it’s a business, a personal blog, or an online store, my goal is to ensure your website helps you reach your goals.</p><br>
        <p>Take a look at what I’ve created — and if you like what you see, let’s build something together. I’m ready to help you build your digital presence today.</p>
        <br>
        <a href="">
        <v-img src="https://i.imgur.com/LXU9Igm.png" style="width: 100%;"></v-img>
        </a>
        <br>
        <v-img src="https://i.imgur.com/dZG4SmN.png" style="width: 100%;"></v-img>
      </v-sheet>
    </div>

    <div ref="fourthRef">
      <v-sheet v-show="showFourth" class="paralax-background fourthSheet animate__animated animate__fadeInUp animate__slower">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          My Development Stack
        </h3><br>
        <br>
        <h3><b style="color: #EEEEEE;">Vue.js</b></h3>
        <p>A progressive JavaScript framework for building user interfaces, used for creating reactive and dynamic web applications.</p><br>
        <h3><b style="color: #EEEEEE;">Vuetify</b></h3>
        <p>A popular Material Design component library for Vue.js, used for creating responsive and aesthetically pleasing user interfaces with minimal effort.</p><br>
        <h3><b style="color: #EEEEEE;">HTML & CSS</b></h3>
        <p>The foundation for web content structure and design. HTML provides semantic markup, while CSS adds advanced styling features for modern, responsive web pages.</p><br>
        <h3><b style="color: #EEEEEE;">JavaScript</b></h3>
        <p>The programming language that powers interactivity and dynamic behavior on web pages.</p><br>
        <h3><b style="color: #EEEEEE;">Node.js</b></h3>
        <p>A JavaScript runtime used for server-side development, useful for handling back-end logic or API interactions.</p><br>
        <h3><b style="color: #EEEEEE;">Git & GitHub</b></h3>
        <p>Version control and collaboration tools to track changes, collaborate with others, and deploy code.</p><br><br>
        <center>
          <v-img src="../assets/document.png" style="width: 25%; display: inline-block"></v-img>
          <v-img src="../assets/html.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/css.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/javascript.png" style="width: 25%; display: inline-block;"></v-img>
          <br><br>
          <v-img src="../assets/nodejs.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/git.png" style="width: 25%; display: inline-block; margin-left: 15px; margin-right: 15px;"></v-img>
          <v-img src="../assets/github.png" style="width: 25%; display: inline-block;"></v-img>
        </center> 
      </v-sheet>
    </div>

  </v-sheet>
</template>

<script>
import { ref, onMounted, nextTick } from 'vue'
import { useDisplay } from 'vuetify'

export default {
  name: 'HelloWorld',
  setup() {
    const { mobile } = useDisplay()
    const menuOpen = ref(false)
    const toggleMenu = () => { menuOpen.value = !menuOpen.value }

    // Show flags for sections
    const showFirst = ref(false)
    const showSecond = ref(false)
    const showThird = ref(false)
    const showFourth = ref(false)

    const firstRef = ref(null)
    const secondRef = ref(null)
    const thirdRef = ref(null)
    const fourthRef = ref(null)

    // IntersectionObserver function
    const observeVisibility = (el, callback) => {
      if (el && el instanceof HTMLElement) {
        const observer = new IntersectionObserver(([entry]) => {
          if (entry.isIntersecting) {
            callback()
            observer.unobserve(entry.target) // prestani pratiti nakon što se prikaže
          }
        }, {
          threshold: 0.3
        })
        observer.observe(el)
      } else {
        console.warn('Element nije validan za IntersectionObserver:', el);
      }
    }

    // Set up observers for each section
    onMounted(() => {
      nextTick(() => {
        if (firstRef.value) {
          observeVisibility(firstRef.value, () => {
            showFirst.value = true
            console.log('First section is now visible')
          })
        }
        if (secondRef.value) {
          observeVisibility(secondRef.value, () => {
            showSecond.value = true
            console.log('Second section is now visible')
          })
        }
        if (thirdRef.value) {
          observeVisibility(thirdRef.value, () => {
            showThird.value = true
            console.log('Third section is now visible')
          })
        }
        if (fourthRef.value) {
          observeVisibility(fourthRef.value, () => {
            showFourth.value = true
            console.log('Fourth section is now visible')
          })
        }
      })
    })

    return {
      mobile,
      menuOpen,
      toggleMenu,
      showFirst,
      showSecond,
      showThird,
      showFourth,
      firstRef,
      secondRef,
      thirdRef,
      fourthRef
    }
  }
}
</script>

<style>
body {
  background-color: #06202b;
}

.background {
  background-color: #06202b;
  min-height: 100vh;
}

#topBar {
  background-color: #06202b;
}

.nav-links {
  gap: 30px;
  margin-left: 20px;
}

.nav-link {
  color: #EEEEEE;
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 12px;
  cursor: pointer;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #F67280;
}

.topBarH1 {
  font-family: 'Cuantico', sans-serif;
  font-size: larger;
  color: #00ADB5;
}

.topBarMenuIcon {
  color: #EEEEEE;
}

.firstSheet,
.secondSheet,
.thirdSheet{
  background-color: #06202b;
  width: 100vw;
  height: auto;
  margin: auto;
  margin-top: 50px;
  text-align: justify;
  overflow: hidden;
  padding: 20px;
}
.fourthSheet{
  background-color: transparent;
  width: 100vw;
  height: auto;
  margin: auto;
  margin-top: 50px;
  text-align: justify;
  overflow: hidden;
  padding: 20px;
}
p {
  color: #EEEEEE;
}
.parallax-background {
  background-image: url("@/assets/technologies.png"); /* Put the link to your image */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 400px; /* Adjust based on your preference */
  overflow: hidden;
}
</style>
