<script lang="ts">
import Vue from "vue";
import myButton from "./component/myButton/myButton.vue";

export default Vue.extend({
  name: "App",
  components: {
    myButton,
  },
  data: () => ({
    message: "Hello !",
    button1: false,
    button2: false,
    button3: false,
    deplacement: "",
    mapping: { un: 1, deux: 2, trois: 3 },
    monStyle: "red",
  }),
  computed: {
    titreBouton: function () {
      return this.button3 ? "Bouton 3 Etat true" : "Bouton 3 Etat false";
    },
  },
  watch: {
    titreBouton2: function () {
      return this.button3 ? "Bouton 3 Etat true" : "Bouton 3 Etat false";
    },
  },
  methods: {
    testMethode: function () {
      return "test";
    },
    test: function () {
      console.log("ici");
      (this.$refs.MonBouton as InstanceType<typeof myButton>)?.testMethode();
      this.monStyle = this.monStyle === "red" ? "yellow" : "red";
    },
  },
  mounted() {
    console.log("création");
  },
});
</script>

<template>
  <v-app>
    <v-main>
      <div v-once>{{ message }}</div>
      <div>{{ deplacement }}</div>
      <div v-if="button1">Bouton 1 click</div>
      <div v-else>Bouton 1 not click</div>
      <div v-show="button2">Bouton 2 click</div>
      <div v-if="button3">Bouton 3 click</div>
      <div class="my-button" @click.stop="test">Bouton1</div>
      <div
        class="my-button"
        @click="button2 = !button2"
        :style="{ backgroundColor: monStyle }"
      >
        Bouton2
      </div>
      <myButton :label="titreBouton" v-model="button3" ref="MonBouton" />
      <div v-for="(value, name) in mapping" :key="name">
        <div v-if="value % 2 !== 0">{{ name }} / {{ value }}</div>
      </div>
    </v-main>
  </v-app>
</template>

<style lang="scss">
.v-main {
  position: relative;
  background-color: var(--primary-grey);
  color: white;
}
.my-button {
  background-color: bisque;
  width: max-content;
  color: black;
  border-radius: 7px;
  padding: 4px;
}
</style>
