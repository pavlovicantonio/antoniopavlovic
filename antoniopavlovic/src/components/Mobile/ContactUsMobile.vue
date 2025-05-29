<script>
import MobileAppBar from "./MobileAppBar.vue";
export default {
  components: {
    MobileAppBar,
  },
};
</script>
<template>
  <v-sheet>
    <v-sheet id="firstVS_CUM" style="width: 100vw; height: 100vh">
      <MobileAppBar />
    </v-sheet>
  </v-sheet>
</template>

<style>
#firstVS_CUM {
  background-image: url("@/assets/template.svg");
}
</style>