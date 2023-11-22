<script lang="ts">
import Vue, { PropType } from "vue";

type Toto = {
  un: string;
  value: boolean;
};
export default Vue.extend({
  name: "myButton",
  props: {
    label: { type: String },
    value: { type: Boolean, default: false },
  },
  methods: {
    testMethode: function () {
      console.log("test");
    },
  },
});
</script>
<template>
  <div
    class="myButton"
    v-on:click="$emit('input', !value)"
    v-on:mouseover="$emit('deplacement')"
  >
    {{ label }}
  </div>
</template>

<style lang="scss">
.myButton {
  background-color: bisque;
  width: max-content;
  color: black;
  border-radius: 7px;
  padding: 4px;
}
</style>
