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
    <v-sheet class="sixthV_Sheet" style="height: 80vh; width: 100vw;">
        <v-sheet class="sixthV_Sheet1">
            <v-sheet class="sixthV_Sheet2">
                <div
          ref="sectionRef"
          :class="{ 'animate__animated animate__fadeInUp': isVisible }"
          style="display: flex; width: 100%; background-color: transparent;"
        >
          <v-sheet style="width: 60vw; background-color: transparent;">
            <h1 class="subheadline text-orange" style="margin-top: 10vh; margin-left: 40px; cursor: default;">Web & Mobile Development</h1>
            <p style="font-size: 1.5rem; padding-left: 40px; margin-top: 5vh; color: #cccccc; text-align: justify; font-family: 'Poppins', sans-serif; cursor: default;">
              I specialize in building modern, responsive websites and mobile-friendly interfaces that not only look great but also provide a smooth user experience across all devices. Whether it's a personal portfolio, a business presentation, or a full-featured web application, my goal is to craft clean and efficient solutions tailored to the needs of each project.
            </p>
          </v-sheet>
          <v-sheet class="align-center justify-center" style="display: flex; width: 40vw; background-color: transparent;">
            <v-img src="../assets/mokcups.png" :class="{ zoomable : isVisible }" style="max-height: 70vh; background-color: transparent;"></v-img>
          </v-sheet>
         
        </div>
            </v-sheet>
        </v-sheet>
    </v-sheet>
</template>

<style>
.sixthV_Sheet{
    background-image: url('../assets/template.svg');
}
.sixthV_Sheet1{
  height: 80vh;
  width: 100vw;
  background-color: rgba(40, 44, 44, 0.95);
} 
.sixthV_Sheet2 {
  height: 60vh;
  width: 95vw;
  background-color: transparent;
  border: 1px solid #FF4500;
  margin-left: auto;
  margin-right: auto;
  border-radius: 5px;
  display: flex;
  align-items: center;
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
</style>