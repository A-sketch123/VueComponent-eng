<template>
  <div>
    <h3>
      I am a grandson component of $attrs/ $listeners, and I receive the value
      of the ancestor component:
    </h3>
    <div>{{ $attrs.message.info }}</div>
  </div>
</template>
<script>
export default {
  name: "grandson",
  data() {
    return {
      grandsonData:
        "I am the value passed from the grandson component to the parent component",
    };
  },
  mounted() {
    this.$emit("grandsonData", this.grandsonData);
  },
};
</script>