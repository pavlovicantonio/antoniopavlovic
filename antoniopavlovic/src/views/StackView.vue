<script setup>
import DesktopStackSheet from '../components/Stack/DesktopStackSheet.vue'
import MobileStack from '@/components/Mobile/MobileStack.vue';
import { useDisplay } from 'vuetify/lib/composables/display';

const {mobile} = useDisplay();

</script>
<template>
  <v-sheet>
    <v-sheet v-if="!mobile">
      <DesktopStackSheet />
    </v-sheet>
    <v-sheet v-else>
      <MobileStack/>
    </v-sheet>
  </v-sheet>
</template>
