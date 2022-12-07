<template>
  <div>
    <button @click="btnClick">Click to pass value to child component 4</button>
    <h2>
      I am component 3, and I want to pass the value to brother component 4
    </h2>
  </div>
</template>
<script>
export default {
  name: "sibling3",
  data() {
    return {
      mes: "I am the data passed from component 3 to component 4",
    };
  },
  methods: {
    btnClick() {
      this.$emit("sibing3click", this.mes);
    },
  },
};
</script>