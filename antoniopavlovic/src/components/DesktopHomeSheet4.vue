<script>
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
      formValid: false, // ⬅️ dodano
      rules: {
        required: (v) => !!v || 'This field is required',
        email: (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      },
    }
  },
  methods: {
    async sendEmail() {
  
    const { valid } = await this.$refs.form.validate()
    if (!valid) return


      this.loading = true

      const selectedServices = [];
      if (this.checked1 == true) selectedServices.push('Website');
      if (this.checked2 == true ) selectedServices.push('Pricing');
      if (this.checked3 == true) selectedServices.push('Consulting');

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
          'service_l5egmq6',     // 🔁 zamijeni svojim SERVICE ID-em
          'template_5aelosk',    // 🔁 zamijeni svojim TEMPLATE ID-em
          templateParams,
          '8Oux9LfPBWiNwRW6F'    // 🔁 zamijeni svojim PUBLIC KEY-em
        )

        alert('Message sent successfully!')
        this.name = ''
        this.email = ''
        this.message = ''
        this.checked1 = false
        this.checked2 = false
        this.checked3 = false
        this.$refs.form.reset() // resetiraj formu
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
  <v-sheet class="seventhV_Sheet">
    <v-sheet class="seventhV_Sheet1" style="margin-bottom: 10vh;">
      <div class="content-wrapper" style="">
        <h1 class="heading">Need a website?</h1>
        <p class="subheading">We build clean, modern solutions for both mobile and desktop.</p>
      </div>
    </v-sheet>
    <v-container style="background-color: transparent; width: 100vw; height: 10vh;">

    </v-container>
    <v-sheet class="seventhV_Sheet2" style="display: flex; align-items: center; justify-content: center;">
      <v-container style="width: 50vw; margin-left: auto; margin-right: auto; height: auto; background-color: rgba(40, 44, 44, 0.4); border: 1px dashed #FF4500;">
        <v-sheet style="width: 40vw; margin-left: auto; margin-right: auto; height: 15vh; background-color: transparent; display: flex; align-items: center;"><h1 style="color: #EEEEEE;">Planning a <span style="color: #FF4500;">project?</span></h1></v-sheet>
        <v-form ref="form" v-model="formValid" style="width: 40vw; margin-left: auto; margin-right: auto;">
          <v-row>
            <v-col>
              <v-text-field
                v-model="name"
                class="custom-field"
                :rules="[rules.required]"
                color="#EEEEEE"
                variant="outlined"
                label="Name:"
                st
              />
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-text-field
               v-model="email"
                class="custom-field"
                :rules="[rules.required, rules.email]"
                color="#EEEEEE"
                variant="outlined"
                label="E-mail:"
              />
            </v-col>
          </v-row>
          <v-row>
            <v-col>
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
            </v-col>
          </v-row>
          <v-row>
            <v-col style="color: #EEEEEE;">Select services you are interested in:</v-col>
          </v-row>
          <v-row>
            <v-col cols="3"><v-checkbox v-model="checked1" class="custom-checkbox" color="#EEEEEE" label="Website"></v-checkbox></v-col>
            <v-col cols="3"><v-checkbox v-model="checked2" class="custom-checkbox" color="#EEEEEE" label="Pricing"></v-checkbox></v-col>
            <v-col cols="3"><v-checkbox v-model="checked3" class="custom-checkbox" color="#EEEEEE" label="Consulting"></v-checkbox></v-col>
          </v-row>
          <v-btn class="botun" block :loading="loading" :disabled="loading" @click="sendEmail()" style="background-color: #EEEEEE; color: #FF4500;">Submit</v-btn>
        </v-form>
        <br>
        <br>
      </v-container>
    </v-sheet>
  </v-sheet>
</template>

<style>
.seventhV_Sheet {
  width: 100vw;
  height: 140vh;
  background-image: url('../assets/template.svg');
}

.seventhV_Sheet1 {
  width: 100vw;
  height: 30vh;
  background-color: transparent;

  display: flex;
  justify-content: center;
  align-items: center;
}

.content-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.heading {
  font-size: 3.5rem;
  font-family: 'Poppins', sans-serif;
  color: #FF4500;
  margin: 0;
}

.subheading {
  font-size: 1.5rem;
  color: #EEEEEE;
  font-family: 'Poppins', sans-serif;
  margin-top: 10px;
}

.seventhV_Sheet2 {
  width: 100vw;
  height: 60vh;
  background-color: transparent;
}

/* Promjena border boje za outlined v-text-field i v-textarea */
.custom-field .v-field__outline {
  border-color: #EEEEEE !important;
}

/* Također postavi CSS varijable za border boju */
.custom-field {
  --v-field-border-color: #EEEEEE !important;
  --v-field-border-hover-color: #EEEEEE !important;
  --v-field-border-focus-color: #EEEEEE !important;
  color: #EEEEEE;
}

/* Stil za labelu */
.custom-field .v-label {
  color: #EEEEEE !important;
}

.custom-checkbox .v-label {
  color: #EEEEEE !important;
}
.custom-checkbox .v-selection-control__input .v-icon {
  color: #EEEEEE !important; /* za "prazni" (unchecked) checkbox */
}

/* Ako želiš da i kad je CHECKED ostane bijelo oko checkboxa: */
.custom-checkbox input:checked + .v-selection-control__input .v-icon {
  color: #EEEEEE !important;
}

.botun:hover{
  background-color: #FF4500;
  color: #EEEEEE;
}

</style>
