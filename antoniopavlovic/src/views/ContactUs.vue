<template>
    <v-sheet>
        <v-sheet v-if="mobile"><ContactUsMobile /></v-sheet>
        <v-sheet v-else><HelloWorld/></v-sheet>
    </v-sheet>
</template>

<script setup>

// Components
import ContactUsMobile from '@/components/Mobile/ContactUsMobile.vue';
import HelloWorld from '@/components/HelloWorld.vue';
import { useDisplay } from 'vuetify'
const {mobile} = useDisplay();


</script>
