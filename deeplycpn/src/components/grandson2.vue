<template>
  <div>
    <h3>
      I am the grandson component of the event bus passing value, and the value
      of the ancestor component I received is:
    </h3>

    <div>{{ passMsg }}</div>
  </div>
</template>
<script>
import { bus } from "../main";
export default {
  name: "grandson",
  data() {
    return {
      passMsg: "",
    };
  },
  // grandson component injection depends on accessing parent component, use provide/inject
  mounted() {
    bus.$on("eventBus", (data) => (this.passMsg = data));
  },
};
</script>