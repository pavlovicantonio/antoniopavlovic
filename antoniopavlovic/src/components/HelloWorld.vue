<script setup>
import DesktopHomeSheet from './DesktopHomeSheet.vue';
import DekstopHomeSheet2 from './DekstopHomeSheet2.vue';
import DesktopHomeSheet3 from './DesktopHomeSheet3.vue';
import DesktopHomeSheet4 from './DesktopHomeSheet4.vue';
import DesktopHomeFooter from './DesktopHomeFooter.vue';
import { useDisplay } from 'vuetify'
import MobileHomePage from './Mobile/MobileHomePage.vue';
const {mobile} = useDisplay();
</script>

<template>
  <v-sheet>
    <v-sheet v-if="mobile">
      <MobileHomePage />
    </v-sheet>
    <v-sheet v-else>
      <DesktopHomeSheet />
      <DekstopHomeSheet2 />
      <DesktopHomeSheet3 />
      <DesktopHomeSheet4 />
      <DesktopHomeFooter />
    </v-sheet>
  </v-sheet>
</template>

<style>

</style>