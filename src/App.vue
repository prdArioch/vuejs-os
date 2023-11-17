<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",
});
</script>

<template>
  <v-app>
    <v-main> Hello word </v-main>
  </v-app>
</template>

<style lang="scss">
.v-main {
  position: relative;
  background-color: var(--primary-grey);
  color: white;
}
</style>
