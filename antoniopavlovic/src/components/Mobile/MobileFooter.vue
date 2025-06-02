<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const redirectTo = (path) => {
  router.push(path).then(() => {
    window.scrollTo({
      top: 0,
      behavior: 'auto' // ili 'smooth' ako želiš glatki prijelaz
    });
  });
};

const sendEmailFooter = () => {
  const email = "apwebing@gmail.com";
  const subject = encodeURIComponent("Ask me anything!");
  const body = encodeURIComponent("Feel free to ask anything you'd like to know.");
  const mailtoLink = `mailto:${email}?subject=${subject}&body=${body}`;

  window.location.href = mailtoLink;
}

const icons = [{ icon: "mdi-facebook", link: "https://www.facebook.com/yourprofile" },
  { icon: "mdi-gmail", action: sendEmailFooter },
  { icon: "mdi-github", link: "https://github.com/pavlovicantonio" },
  { icon: "mdi-instagram", link: "https://www.instagram.com/apwebing" },];
</script>


<template>
  <v-footer
    class="text-center d-flex flex-column ga-2 py-4"
    style="background-color: rgba(40, 44, 44, 0.85)"
  >
    <div class="d-flex ga-3">
      <template v-for="social in icons" :key="social.icon">
        <a
          v-if="social.link"
          :href="social.link"
          target="_blank"
          rel="noopener noreferrer"
        >
          <v-btn
            :icon="social.icon"
            density="comfortable"
            variant="text"
            style="color: #ff4500"
          />
        </a>

        <v-btn
          v-else-if="social.action"
          :icon="social.icon"
          @click="social.action"
          density="comfortable"
          variant="text"
          style="color: #ff4500"
        />
      </template>
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
      <span @click="redirectTo('/stack')"
      style="color: #ff4500; text-decoration: none; "
        >
          Dev Stack
        </span
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