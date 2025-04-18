<template>
  <v-sheet v-if="mobile" class="background">
    
    <v-sheet id="topBar" class="pa-4 d-flex align-center justify-space-between">
      <div class="d-flex align-center">
        <h1 v-show="!menuOpen" class="topBarH1 animate__animated animate__fadeInDown">Antonio Pavlović</h1>

        <!-- Navigacija koja se prikazuje kad je menuOpen true -->
        <div
          v-if="menuOpen"
          class="ml-4 d-flex align-center nav-links animate__animated animate__fadeInLeft"
        >
          <span class="nav-link">CONTACT</span>
          <span class="nav-link">ABOUT ME</span>
          <span class="nav-link">MY WORK</span>
        </div>
      </div>
      <v-icon class="topBarMenuIcon animate__animated animate__backInRight animate__delay-0.5s" style="color: #EEEEEE" @click="toggleMenu">{{ menuOpen ? 'mdi-close' : 'mdi-menu' }}</v-icon>
    </v-sheet>

    <v-sheet v-if="showContent" class="firstSheet">
      <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important; ">Why did I make my own website?</h3><br>
      <p class="animate__animated animate__zoomIn" style="font-family: 'Inter', sans-serif !important;">It all began when I dove into studying and started building websites. Before long, a few friends asked me to create sites for them, they liked my style and approach. That sparked an idea: why not build my own personal website? A place where I can share a bit about who I am and leave a form for anyone who’s dreaming of having their own custom site. If that’s you, let’s make it happen.</p>
    </v-sheet>

    <v-sheet v-if="showContent" class="secondSheet">
      <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important; ">Looking for your own website?</h3><br>
      <p class="animate__animated animate__slideInLeft" style="font-family: 'Inter', sans-serif !important;">In today’s digital world, having a professional website is a must for businesses, personal brands, and creatives alike. Whether you're looking to showcase your portfolio, sell products, or share your ideas with the world, I can help you bring your vision to life.</p>
      <br>
      <p class="animate__animated animate__slideInRight" style="font-family: 'Inter', sans-serif !important;">Let’s build a website that not only looks amazing but also works flawlessly across all devices. Ready to take the next step? Contact me today, and let’s create something great together!</p>
    </v-sheet>

    
    <v-sheet class="thirdSheet">
      <h3 class="animate__animated animate__zoomInDown" style="color: #F67280; font-family: 'Inter', sans-serif !important; ">My products</h3><br>
      <center>
        <v-img src="../assets/programmer.gif" style="width: 30%; display: inline-block"></v-img>
        <v-img src="../assets/arrow.gif" style="width: 30%; display: inline-block;"></v-img>
        <v-img src="../assets/product.gif" style="width: 30%; display: inline-block;"></v-img>
      </center> 
      <br>
      <p>Here are some of the websites I’ve built so far.</p><br>
      <p>Each project reflects a unique vision — whether it’s for a friend, a business, or just a creative idea. I’m always aiming to combine clean design with smooth functionality.</p><br>
      <p>Take a look at what I’ve created — and if you like what you see, let’s build something together.</p>
    </v-sheet>

  </v-sheet>
</template>

<script>
import { useDisplay } from 'vuetify'
import { ref, onMounted } from 'vue'


export default {
  name: 'HelloWorld',
  setup() {
    const { mobile } = useDisplay();
    const showContent = ref(false);
    const menuOpen = ref(false);

    const toggleMenu = () => {
      menuOpen.value = !menuOpen.value;
    };

    onMounted(() => {
      setTimeout(() => {
        showContent.value = true
      }, 1000)
    })

    return { mobile, showContent, menuOpen, toggleMenu}
  },
}
</script>

<style>

body{
  background-color: #06202b;
}

.background{
  background-color: #06202b;
  height: 100vh;
}

#topBar{
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

.topBarH1{
    font-family: 'Cuantico', sans-serif;
    font-size: larger;
    color: #00ADB5;
}

.topBarMenuIcon{
  color: #EEEEEE;
}

.firstSheet {
  background-color: #06202b;
  width: 100vw;
  height: auto;
  margin: auto;
  margin-top: 30px;
  text-align: justify ;
  overflow: hidden;
  padding: 20px; /* Dodajte malo prostora unutra */
}

.secondSheet {
  background-color: #06202b;
  width: 100vw;
  height: auto;
  margin: auto;
  margin-top: 30px;
  text-align: justify ;
  overflow: hidden;
  padding: 20px; /* Dodajte malo prostora unutra */
}

.thirdSheet {
  background-color: #06202b;
  width: 100vw;
  height: auto;
  margin: auto;
  margin-top: 30px;
  text-align: justify ;
  overflow: hidden;
  padding: 20px; /* Dodajte malo prostora unutra */
}

p{
  color: #EEEEEE;
}
</style>