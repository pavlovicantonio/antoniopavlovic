<script setup>
const redirectTo = (path) => {
  window.location.href = path;
};

const icons = ["mdi-facebook", "mdi-gmail", "mdi-github", "mdi-instagram"];
</script>

<template>
  <v-footer
    class="text-center d-flex flex-column ga-2 py-4"
    style="background-color: rgba(40, 44, 44, 0.85)"
  >
    <div class="d-flex ga-3">
      <v-btn
        v-for="icon in icons"
        :key="icon"
        :icon="icon"
        density="comfortable"
        variant="text"
        style="color: #ff4500"
      ></v-btn>
    </div>

    <v-divider class="my-2" thickness="2" width="50"></v-divider>

    <div
      class="text-caption font-weight-regular opacity-90"
      style="color: #ff4500; cursor: default"
    >
      <span
        @click="redirectTo('/')"
        style="color: #ff4500; text-decoration: none"
        >Home</span
      >
      |
      <span
        @click="redirectTo('/contact')"
        style="color: #ff4500; text-decoration: none"
        >Contact Us</span
      >
      |
      <span
        ><a href="https://github.com/pavlovicantonio" target="_blank" style="text-decoration: none; color: #ff4500"
          >Github</a
        ></span
      >
      |
      <span
        ><a href="" style="text-decoration: none; color: #ff4500"
          >Dev Stack</a
        ></span
      >
    </div>

    <v-divider class="my-2" thickness="2" width="50"></v-divider>

    <div style="color: #ff4500; cursor: default">
      © All Rights Reserved {{ new Date().getFullYear() }} —
      <strong
        ><a href="https://apwebing.netlify.app" style="text-decoration: none; color: #ff4500;"
          >APWebing</a
        ></strong
      >
    </div>
  </v-footer>
</template>