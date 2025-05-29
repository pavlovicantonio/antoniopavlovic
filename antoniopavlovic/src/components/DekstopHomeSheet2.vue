<script setup>
import { ref, onMounted } from 'vue'

const isVisible = ref(false)
const sectionRef = ref(null)

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          isVisible.value = true
        }
      })
    },
    { threshold: 0.4 }
  )

  if (sectionRef.value) {
    observer.observe(sectionRef.value)
  }
})
</script>

<template>
  <v-sheet class="fourthV_Sheet" style="height: auto; width: 100vw;">
    <v-sheet class="fifthV_Sheet" style="height: auto;">
      <v-sheet class="fifthV_Sheet1">
        <div class="headline">
          <span class="text-white font-weight-bold" style="cursor: default;">Our</span>
          <span class="text-orange font-weight-bold" style="cursor: default;">work</span>
        </div>
        <div class="subheadline" style="cursor: default;">
          Check out some of our favourite projects
        </div>
      </v-sheet>

      <v-sheet class="fifthV_Sheet2" style="background-color: transparent; margin-bottom: 10vh;">
        <div
          ref="sectionRef"
          :class="{ 'animate__animated animate__fadeInUp': isVisible }"
          style="display: flex; width: 100%; background-color: transparent;"
        >
          <v-sheet class="align-center justify-center" style="display: flex; width: 40vw; background-color: transparent;">
            <v-img src="../assets/pc.png" :class="{ zoomable : isVisible }" style="max-height: 70vh; background-color: transparent;"></v-img>
          </v-sheet>
          <v-sheet style="width: 60vw; background-color: transparent;">
            <h1 class="subheadline text-orange" style="margin-top: 10vh; cursor: default;">Technologies I Use</h1>
            <p style="font-size: 1.5rem; padding-right: 40px; margin-top: 5vh; color: #cccccc; cursor: default; text-align: justify; font-family: 'Poppins', sans-serif;">
              As a computer science student with a strong passion for web development, I constantly strive to learn and improve.
              Every project is an opportunity for me to grow, and I give my full dedication to creating thoughtful, user-friendly websites.
              I primarily work with modern technologies like Vue.js and Vuetify to build clean, responsive interfaces.
            </p>
          </v-sheet>
        </div>
      </v-sheet>
    </v-sheet>
  </v-sheet>
</template>

<style scoped>
.fourthV_Sheet {
  background-color: transparent;
  background-image: url('@/assets/template.svg');
  background-size: cover;
  background-position: center;
  display: flex;
  height: auto;
}

.fifthV_Sheet {
  height: 70vh;
  width: 100vw;
  background-color: rgba(40, 44, 44, 0.95);
}

.fifthV_Sheet1 {
  height: auto;
  width: 100vw;
  background-color: transparent;
  padding: 100px 40px;
  text-align: left;
  letter-spacing: 2px;
}

.headline {
  font-size: 3.5rem;
  font-family: 'Poppins', sans-serif;
  display: flex;
  gap: 10px;
}

.text-orange {
  color: #FF4500;
}

.subheadline {
  font-size: 2.5rem;
  margin-top: 10px;
  color: #cccccc;
  font-family: 'Poppins', sans-serif;
}

.fifthV_Sheet2 {
  height: 70vh;
  width: 95vw;
  background-color: transparent;
  border: 1px solid #FF4500;
  margin-left: auto;
  margin-right: auto;
  border-radius: 5px;
  display: flex;
  align-items: center;
}

.zoomable:hover{
  transform: scale(1.35);
  opacity: 1;
  transition: transform 0.8s ease, opacity 0.8s ease;
}
</style>
