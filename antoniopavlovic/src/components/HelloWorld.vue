<template>
  <v-sheet v-if="mobile" class="background">
    <v-sheet id="topBar" class="pa-4 d-flex align-center justify-space-between" style="position: fixed; top: 0; right: 0; left: 0; z-index: 5;">
      <div class="d-flex align-center">
        <h1 v-show="!menuOpen" class="topBarH1 animate__animated animate__fadeInDown">
          Antonio Pavlović
        </h1>

        <div v-if="menuOpen" class="ml-4 d-flex align-center nav-links animate__animated animate__fadeInLeft">
          <span class="nav-link" @click="scrollToSection('sixth')">CONTACT</span>
          <span class="nav-link" @click="scrollToSection('fifth')">ABOUT ME</span>
          <span class="nav-link" @click="scrollToSection('third')">MY PRODUCTS</span>
        </div>
      </div>
      <v-icon class="topBarMenuIcon animate__animated animate__backInRight animate__delay-0.5s" style="color: #EEEEEE" @click="toggleMenu">
        {{ menuOpen ? 'mdi-close' : 'mdi-menu' }}
      </v-icon>
    </v-sheet>

    <!-- First Section -->
    <div ref="firstRef">
      <v-sheet v-show="showFirst" class="firstSheet">
        <br><br>
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          Why did I make my own website? 👨‍💻
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
          Looking for your own website? 🚀
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
    <div ref="thirdRef" class="scroll-target">
      <v-sheet v-show="showThird" class="thirdSheet animate__animated animate__fadeInUp animate__slower">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          My products 💻
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
          My Development Stack 🛠️
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
        <p>Version control and collaboration tools to track changes, collaborate with others, and deploy code.</p><br>
        <h3><b style="color: #EEEEEE;">Firebase</b></h3>
        <p>A powerful platform by Google that provides backend services like authentication, real-time databases, and hosting. Perfect for quickly deploying full-featured web apps.</p><br>
        <h3><b style="color: #EEEEEE;">Visual Studio Code</b></h3>
        <p>My go-to code editor. Lightweight, highly customizable, and packed with extensions that make developing modern web applications faster and more efficient</p>
        <br><br>
        <center>
          <v-img src="../assets/document.png" style="width: 25%; display: inline-block"></v-img>
          <v-img src="../assets/html.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/css.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/javascript.png" style="width: 25%; display: inline-block;"></v-img>
          <br><br>
          <v-img src="../assets/nodejs.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/git.png" style="width: 25%; display: inline-block; margin-left: 15px; margin-right: 15px;"></v-img>
          <v-img src="../assets/github.png" style="width: 25%; display: inline-block;"></v-img>
          <br><br>
          <v-img src="../assets/firebase.png" style="width: 25%; display: inline-block;"></v-img>
          <v-img src="../assets/visual-studio.png" style="width: 25%; display: inline-block;"></v-img>
          <br><br>
          <v-img src="../assets/vuetify.png" style="width: 25%; display: inline-block;"></v-img>
        </center> 
      </v-sheet>
    </div>

    <div ref="fifthRef" class="scroll-target">
      <v-sheet v-show="showFifth" class="fifthSheet animate__animated animate__fadeInUp animate__slower">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          About Me 👨‍💻
        </h3><br>
        <p class="animate__animated animate__zoomIn" style="font-family: 'Inter', sans-serif !important;">
          Hi! I'm Antonio Pavlović, a 23-year-old Computer Science student at the University of Juraj Dobrila in Pula. I’m passionate about football and building websites. Although I’m not an expert yet, I’m constantly learning and honing my skills.
        </p><br>
        <p class="animate__animated animate__zoomIn" style="font-family: 'Inter', sans-serif !important;">
          I started diving into web development a while ago and it quickly became something I truly enjoy. I'm focused on improving my abilities and creating websites that help people express themselves and their businesses online.
        </p><br>
      </v-sheet>
    </div>

    <!-- Sixth Section - Contact Form -->
    <div ref="sixthRef" class="scroll-target">
      <v-sheet v-show="showSixth" class="sixthSheet animate__animated animate__fadeInUp animate__slower" style="padding: 16px; background-color: #06202b;;">
        <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important;">
          Let's get in touch 📬
        </h3><br>
        <p style="font-family: 'Inter', sans-serif !important;">If you're looking to create your own website, feel free to send an inquiry through the form below. I'd be happy to help you build an online presence that suits your needs!</p>
        <br><br>
        <v-form @submit.prevent="sendEmail()" ref="contactForm">
          <v-text-field
            v-model="form.name"
            label="Your Name"
            required
            outlined
            :style="{ color: '#EEEEEE', '--v-theme-primary': '#EEEEEE', '--v-input-control-border-color': '#EEEEEE' }"
          ></v-text-field>

          <v-text-field
            v-model="form.email"
            label="Email Address"
            required
            outlined
            color="primary"
            type="email"
            :style="{ color: '#EEEEEE', '--v-theme-primary': '#EEEEEE', '--v-input-control-border-color': '#EEEEEE' }"
          ></v-text-field>

          <v-textarea
            v-model="form.message"
            label="Your Message"
            required
            outlined
            color="primary"
            rows="5"
            :style="{ color: '#EEEEEE', '--v-theme-primary': '#EEEEEE', '--v-input-control-border-color': '#EEEEEE' }"
          ></v-textarea>

          <v-btn
          color="#F67280"
          class="mt-4"
          type="submit"
          block
          :loading="loading"
          :disabled="loading"
        >
          {{ loading ? 'Sending...' : 'Send Message' }}
        </v-btn>
        </v-form>

        <p style="font-family: 'Inter', sans-serif !important; margin-top: 45px; margin-bottom: 70px;">You can also <b style="color: #F67280;">contact me via</b> email or social media — whichever works best for you. I'm here to help you bring your ideas to life!</p>
        <center>
          <div style="margin-bottom: 80px;">
            <v-img class="icons" src="../assets/instagram.png" style="width: 10%; display: inline-block; margin: 20px;"></v-img>
            <v-img class="icons" src="../assets/gmail1.png" style="width: 10%; display: inline-block; margin: 20px;"></v-img>
            <v-img class="icons" src="../assets/whatsapp.png" style="width: 10%; display: inline-block; margin: 20px;"></v-img>
            <v-img class="icons" src="../assets/viber.png" style="width: 10%; display: inline-block; margin: 20px;"></v-img>
          </div>
        </center> 
      </v-sheet>
    </div>
  </v-sheet>
</template>

<script>
import { ref, onMounted, nextTick } from 'vue'
import { useDisplay } from 'vuetify'
import emailjs from '@emailjs/browser'
import { reactive } from 'vue'

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
    const showFifth = ref(false)
    const showSixth = ref(false)

    const firstRef = ref(null)
    const secondRef = ref(null)
    const thirdRef = ref(null)
    const fourthRef = ref(null)
    const fifthRef = ref(null)
    const sixthRef = ref(null)

    const form = reactive({
      name: '',
      email: '',
      message: ''
    })

    const loading = ref(false) // <-- ovo je za loading stanje

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
        if (fifthRef.value) {
          observeVisibility(fifthRef.value, () => {
            showFifth.value = true
            console.log('Fifth section is now visible')
          })
        }
        if (sixthRef.value) {
          observeVisibility(sixthRef.value, () => {
            showSixth.value = true
            console.log('Sixth section is now visible')
          })
        }
      })
    })

    const scrollToSection = (section) => {
      let sectionRef = null;
      if (section === 'first') sectionRef = firstRef.value;
      if (section === 'second') sectionRef = secondRef.value;
      if (section === 'third') sectionRef = thirdRef.value;
      if (section === 'fourth') sectionRef = fourthRef.value;
      if (section === 'fifth') sectionRef = fifthRef.value;
      if (section === 'sixth') sectionRef = sixthRef.value;

      if (sectionRef) {
        sectionRef.scrollIntoView({ behavior: 'smooth', block: 'start' });
        menuOpen.value = false; // automatski zatvori meni ako je otvoren
      }
    };

    const sendEmail = async () => {
      loading.value = true
      const templateParams = {
        name: form.name,
        email: form.email,
        message: form.message,
        title: 'New Contact Message',
        time: new Date().toLocaleString(),
      }

      try {
        await emailjs.send(
          'service_tq98dek',     // 🔁 zamijeni svojim service ID-em
          'template_fhe0lsf',    // 🔁 zamijeni svojim template ID-em
          templateParams,
          'sFLXs5tV3k0YzQFA7'      // 🔁 zamijeni svojim public key-em
        )

        alert('Message sent successfully!')
        form.name = ''
        form.email = ''
        form.message = ''
      } catch (error) {
        console.error('Email send error:', error)
        alert('Failed to send message.')
      } finally {
        loading.value = false
      }
    }

    return {
      mobile,
      menuOpen,
      toggleMenu,
      showFirst,
      showSecond,
      showThird,
      showFourth,
      showFifth,
      firstRef,
      secondRef,
      thirdRef,
      fourthRef,
      fifthRef,
      sixthRef,
      showSixth,
      form,
      loading,
      sendEmail,
      scrollToSection
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

.icons:hover{
  transform: scale(1.4);
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
.thirdSheet,
.fifthSheet{
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
.seventhSheet{
  height: 200px;
  background: linear-gradient(180deg,rgba(6, 32, 43, 1) 12%, rgba(16, 16, 74, 1) 34%, rgba(23, 23, 99, 1) 80%);
}
.scroll-target {
  scroll-margin-top: 30px;
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
