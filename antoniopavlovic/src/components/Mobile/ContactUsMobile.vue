<script>
import MobileAppBar from './MobileAppBar.vue'
import MobileFooter from './MobileFooter.vue'
import emailjs from 'emailjs-com'

export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
      checked1: false,
      checked2: false,
      checked3: false,
      loading: false,
      formValid: false,
      rules: {
        required: (v) => !!v || 'This field is required',
        email: (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      },
    }
  },
  components: {
    MobileFooter,
    MobileAppBar
  },
  methods: {
    async sendEmail() {
      const { valid } = await this.$refs.form.validate()
      if (!valid) return

      this.loading = true
      const selectedServices = []
      if (this.checked1) selectedServices.push('Website')
      if (this.checked2) selectedServices.push('Pricing')
      if (this.checked3) selectedServices.push('Consulting')

      const templateParams = {
        name: this.name,
        email: this.email,
        message: this.message,
        services: selectedServices,
        title: 'New Message',
        time: new Date().toLocaleString(),
      }

      try {
        await emailjs.send(
          'service_l5egmq6',
          'template_5aelosk',
          templateParams,
          '8Oux9LfPBWiNwRW6F'
        )

        alert('Message sent successfully!')
        this.name = ''
        this.email = ''
        this.message = ''
        this.checked1 = false
        this.checked2 = false
        this.checked3 = false
        this.$refs.form.reset()
      } catch (error) {
        console.error('Email send error:', error)
        alert('Failed to send message.')
      } finally {
        this.loading = false
      }
    }
  }
}
</script>

<template>
  <v-sheet>
    <v-sheet id="firstVS_CUM" style="width: 100vw; height: 100%; background-color: transparent;">
      <MobileAppBar />
      <v-sheet class="mobileV_Sheet" style="background-color: transparent;">
        <v-sheet class="mobileV_Header d-flex align-center justify-center" style="background-color: transparent; margin-top: 5vh; margin-bottom: 5vh;">
          <div class="content-wrapper" style="background-color: transparent;">
            <h1 class="mobile-heading">Need a website?</h1>
            <p class="mobile-subheading">We build clean, modern solutions for mobile and desktop.</p>
          </div>
        </v-sheet>

        <v-sheet class="mobileV_Content d-flex justify-center" style="background-color: transparent;">
          <v-container class="mobile-container" style="background-color: transparent;">
            <v-sheet class="d-flex justify-center" style="background-color: transparent;">
              <h2 class="mobile-form-title">Planning a <span style="color: #FF4500;">project?</span></h2>
            </v-sheet>
            <v-form ref="form" v-model="formValid">
              <v-text-field
                v-model="name"
                class="custom-field"
                :rules="[rules.required]"
                color="#EEEEEE"
                variant="outlined"
                label="Name:"
              />
              <v-text-field
                v-model="email"
                class="custom-field"
                :rules="[rules.required, rules.email]"
                color="#EEEEEE"
                variant="outlined"
                label="E-mail:"
              />
              <v-textarea
                v-model="message"
                class="custom-field"
                :rules="[rules.required]"
                color="#EEEEEE"
                variant="outlined"
                label="Describe your project"
                rows="3"
                auto-grow
              />
              <div style="color: #EEEEEE; margin-top: 1rem;">Select services:</div>
              <v-checkbox
                v-model="checked1"
                class="custom-checkbox"
                color="#EEEEEE"
                label="Website"
              />
              <v-checkbox
                v-model="checked2"
                class="custom-checkbox"
                color="#EEEEEE"
                label="Pricing"
              />
              <v-checkbox
                v-model="checked3"
                class="custom-checkbox"
                color="#EEEEEE"
                label="Consulting"
              />
              <v-btn
                class="botun"
                block
                :loading="loading"
                :disabled="loading"
                @click="sendEmail"
              >
                Submit
              </v-btn>
            </v-form>
          </v-container>
        </v-sheet>
      </v-sheet>
      <MobileFooter />
    </v-sheet>
  </v-sheet>
</template>

<style>
#firstVS_CUM {
  background-image: url("@/assets/template.svg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  overflow-y: auto;
}

.mobileV_Sheet {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  min-height: 0; /* važno za flex container */
  background-color: rgba(40, 44, 44, 0.9);
  padding: 2rem 1rem;
}

.mobileV_Header {
  padding-top: 2rem;
  text-align: center;
}

.mobile-heading {
  font-size: 2rem;
  font-family: 'Poppins', sans-serif;
  color: #FF4500;
  margin: 0;
}

.mobile-subheading {
  font-size: 1rem;
  font-family: 'Poppins', sans-serif;
  color: #EEEEEE;
  margin-top: 0.5rem;
}

.mobileV_Content {
  padding-bottom: 4rem;
  flex: 1;
  display: flex;
  justify-content: center;
}

.mobile-container {
  width: 100%;
  max-width: 500px;
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px dashed #FF4500;
  border-radius: 12px;
  padding: 1.5rem;
  overflow-y: auto;
}

.mobile-form-title {
  color: #EEEEEE;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

/* Custom field + checkbox styling (iz desktop verzije) */
.custom-field .v-field__outline {
  border-color: #EEEEEE !important;
}

.custom-field {
  --v-field-border-color: #EEEEEE !important;
  --v-field-border-hover-color: #EEEEEE !important;
  --v-field-border-focus-color: #EEEEEE !important;
  color: #EEEEEE;
}

.custom-field .v-label,
.custom-checkbox .v-label {
  color: #EEEEEE !important;
}

.custom-checkbox .v-selection-control__input .v-icon {
  color: #EEEEEE !important;
}

.botun {
  background-color: #EEEEEE;
  color: #FF4500;
  margin-top: 1rem;
}

.botun:hover {
  background-color: #FF4500;
  color: #EEEEEE;
}
</style>
