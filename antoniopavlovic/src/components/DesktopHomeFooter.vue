<script setup>
import logo from '../assets/apwebing3.png'
</script>

<template>
  <v-sheet class="eighthV_Sheet" style="margin-left: auto; margin-right: auto;">
    <v-footer class="footer pa-6" height="auto">
      <v-container fluid class="px-4" style="max-width: 98vw; height: 100%;">
        <v-row class="justify-space-between align-start mb-6" no-gutters style="height: 100%;">
          <!-- Kontakt informacije lijevo -->
          <v-col cols="12" md="4" class="d-flex flex-column justify-start" style="height: 100%; gap: 1rem;">
            <div class="d-flex align-center">
              <v-icon color="orange-darken-2" size="24">mdi-map-marker</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Find us</h4>
                <span class="text-grey-lighten-1 text-body-2">Coming soon</span>
              </div>
            </div>

            <div class="d-flex align-center">
              <v-icon color="orange-darken-2" size="24">mdi-phone</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Call us</h4>
                <span class="text-grey-lighten-1 text-body-2">0993427477</span>
              </div>
            </div>

            <div class="d-flex align-center">
              <v-icon color="orange-darken-2" size="24">mdi-email-open</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Mail us</h4>
                <span class="text-grey-lighten-1 text-body-2">apwebing@gmail.com</span>
              </div>
            </div>
          </v-col>

          <!-- Logo i copyright -->
          <v-col
            cols="12"
            md="4"
            class="d-flex flex-column align-center justify-center"
            style="height: 100%; min-height: 120px;"
          >
            <v-img
              :src="logo"
              style="max-width: 200px;"
              alt="logo"
            />
            <p class="text-grey-lighten-1 text-body-2 text-center" style="margin-top: 1rem; font-size: 0.85rem;">
              © 2025 All Rights Reserved
              <a href="https://apwebing.netlify.app" class="text-orange-darken-2 text-decoration-none">APWebing</a>
            </p>
          </v-col>
          <!-- Društvene mreže desno -->
          <v-col
            cols="12"
            md="4"
            class="text-md-end text-center d-flex align-items-center justify-md-end"
            style="height: 100%;"
          >
            <div class="d-flex justify-center justify-md-end align-items-center" style="gap: 16px; margin-top: 80px;">
              <v-btn icon class="social-btn facebook" variant="flat">
                <v-icon size="28">mdi-facebook</v-icon>
              </v-btn>
              <v-btn icon class="social-btn twitter" variant="flat">
                <v-icon size="28">mdi-gmail</v-icon>
              </v-btn>
              <v-btn icon class="social-btn google" variant="flat">
                <v-icon size="28">mdi-instagram</v-icon>
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
    <v-sheet class="margin"></v-sheet>
  </v-sheet>
</template>

<style scoped>
.eighthV_Sheet {
  width: 100vw;
  height: 32vh; /* smanjena visina */
  background-image: url('../assets/template.svg');
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.footer {
  background-color: #151414;
  width: 98vw;
  height: 100%;
  padding-top: 1rem;
  padding-bottom: 1rem;
}

.social-btn {
  color: white;
  border-radius: 50%;
  height: 48px;
  width: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
}

.facebook {
  background-color: #3B5998;
}
.twitter {
  background-color: #55ACEE;
}
.google {
  background-color: #DD4B39;
}
</style>
