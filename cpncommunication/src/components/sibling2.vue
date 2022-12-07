<template>
  <div>
    <h1>sibling2</h1>
    <p>{{ receiveValue }}</p>
  </div>
</template>
<script>
import { bus } from "../main";
export default {
  name: "sibling2",
  data() {
    return {
      receiveValue:
        "I am subcomponent 2, after clicking the button of subcomponent 1, I will become the data from subcomponent 1",
    };
  },
  mounted() {
    // The event bus handle event registered in the sibling component;
    bus.$on("handle", (data) => {
      console.log("params: ", data);
      this.receiveValue = data;
    });
  },
};
</script>