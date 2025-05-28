<template>
  <v-sheet class="background-wrapper">
    <v-app-bar
  flat
  elevate-on-scroll
  class="custom-app-bar d-flex align-center px-4"
>
      <v-img
        src="@/assets/apwebing2.png"
        alt="Logo"
        height="55"
        style="max-width: 180px;"
      ></v-img>

      <v-spacer></v-spacer>

      <v-btn color="#EEEEEE">NEŠTO</v-btn>
      <v-btn color="#EEEEEE">NEŠTO</v-btn>
      <v-btn color="#EEEEEE">NEŠTO</v-btn>

      <v-spacer></v-spacer>

      <v-btn color="#EEEEEE">Nešto</v-btn>
    </v-app-bar>

    <v-sheet class="fVS" style="height: 95vh; width: 100vw;">
      <v-sheet style="background-color: transparent; display: flex; justify-content: center; align-items: center; height: 95vh; width: 40vw;"> 
        <div class="headline-wrapper" style="padding: 100px;">
          <div class="word">GRASP</div>
          <div class="word">YOUR</div>
          <div class="word highlight">DIGITAL</div>
          <div class="word">FUTURE</div>
        </div>
      </v-sheet>
      <v-sheet style="display: flex; height: 95vh; width: 60vw;">
        <!-- desna strana prazna -->
      </v-sheet>
    </v-sheet>
  </v-sheet>
</template>

<style scoped>
.background-wrapper {
  background-image: url('@/assets/template.svg');
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  width: 100vw;
}

.custom-app-bar {
  background-color: transparent;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-size: cover;
  background-position: center;
  z-index: 10;
}

.headline-wrapper {
  display: flex;
  flex-direction: column;
  align-items: left;
  text-align: left;
  gap: 8px;
}

.word {
  font-family: 'Anton', sans-serif;
  font-size: 4.5rem;
  letter-spacing: 12px;
  color: #EEEEEE;
}

.word:hover {
  color: #FF4500;
}

.highlight {
  color: #FF4500;
}

.highlight:hover {
  color: #EEEEEE;
}
</style>
