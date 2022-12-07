<template>
  <div>
    <h3>{{ passmes }}</h3>
  </div>
</template>
<script>
export default {
  name: "sibling4",
  props: ["mes"],
  computed: {
    passmes() {
      if (this.mes == "") {
        return "I am sub-component 3, clicking the sub-component 4 button will pass the value to me to change my value";
      } else {
        return this.mes;
      }
    },
  },
};
</script>