<template>
  <!-- Sibling component value passing: event bus method -->
  <div>
    <button @click="submitData">Click to send</button>
    <h1>sibling1</h1>
  </div>
</template>
<script>
// import event bus
import { bus } from "../main";
export default {
  name: "sibling1",
  data() {
    return {
      mes: "I am the data sent by child component 1 to sibling components",
    };
  },
  methods: {
    submitData() {
      // When the click event is triggered, pass the value to the sibling component through $emit;
      bus.$emit("handle", this.mes);
    },
  },
  destroyed() {
    bus.$off("handle"); // Destroy the listening event before the component is destroyed
  },
};
</script>