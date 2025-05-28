<template>
  <v-sheet class="eighthV_Sheet" style="margin-left: auto; margin-right: auto;">
    <v-footer class="footer pa-6" height="auto">
    <v-container fluid class="px-4" style="max-width: 98vw">
      <v-row class="justify-space-between align-center mb-6" no-gutters>
        <!-- Kontakt informacije (sve u jednom redu) -->
        <v-col cols="12" md="8">
          <v-row class="flex-wrap" justify="start" align="center" no-gutters>
            <!-- Find us -->
            <div class="d-flex align-center me-10 mb-4 mb-md-0">
              <v-icon color="orange-darken-2" size="28">mdi-map-marker</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Find us</h4>
                <span class="text-grey-lighten-1 text-body-2">Coming soon</span>
              </div>
            </div>

            <!-- Call us -->
            <div class="d-flex align-center me-10 mb-4 mb-md-0">
              <v-icon color="orange-darken-2" size="28">mdi-phone</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Call us</h4>
                <span class="text-grey-lighten-1 text-body-2">0993427477</span>
              </div>
            </div>

            <!-- Mail us -->
            <div class="d-flex align-center">
              <v-icon color="orange-darken-2" size="28">mdi-email-open</v-icon>
              <div class="ms-2">
                <h4 class="text-white text-subtitle-2 font-weight-medium mb-1">Mail us</h4>
                <span class="text-grey-lighten-1 text-body-2">apwebing@gmail.com</span>
              </div>
            </div>
          </v-row>
        </v-col>

        <!-- Logo + opis + društvene mreže -->
        <v-col cols="12" md="4" class="text-md-end text-center">
          <a
  href="https://apwebing.netlify.app"
  target="_blank"
  rel="noopener"
  style="display: block;"
><v-img
            src="../assets/apwebing3.png"
            max-width="120"
            class="mx-auto mb-5"
            alt="logo"
          /></a>
          <div class="d-flex justify-center justify-md-center">
            <v-btn icon class="social-btn facebook me-2" variant="flat">
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
            <v-btn icon class="social-btn twitter me-2" variant="flat">
              <v-icon>mdi-gmail</v-icon>
            </v-btn>
            <v-btn icon class="social-btn google" variant="flat">
              <v-icon>mdi-instagram</v-icon>
            </v-btn>
          </div>
        </v-col>
      </v-row>

      <v-divider class="my-4" />

      <!-- Copyright -->
      <v-row justify="center">
        <p class="text-grey-lighten-1 text-body-2 text-center">
          © 2025 All Rights Reserved <a href="https://apwebing.netlify.app" class="text-orange-darken-2 text-decoration-none">APWebing</a>
        </p>
      </v-row>
    </v-container>
  </v-footer>
    <v-sheet class="margin"></v-sheet>
  </v-sheet>
</template>

<style scoped>
.eighthV_Sheet {
  width: 100vw;
  height: 41vh;
  background-image: url('../assets/template.svg');
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.eighthV_Sheet1 {
  width: 98vw;
  height: 40vh;
  background-color: rgba(40, 44, 44, 0.95);
  border-radius: 10px;
  margin-left: auto;
  margin-right: auto;
  padding: 24px 16px;
  box-sizing: border-box;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.footer {
  background-color: #151414;
  width: 98vw;
}

.social-btn {
  color: white;
  border-radius: 50%;
  height: 40px;
  width: 40px;
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