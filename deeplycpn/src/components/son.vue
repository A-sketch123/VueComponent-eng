<template>
  <div>
    <!-- Method 1: provide / inject -->
    <grandson></grandson>

    <!-- Method 2: Central event bus, use the method to pass values with sibling components -->
    <!-- <grandson2></grandson2> -->

    <!-- Method 3: Use $attrs/ $listeners -->
    <!-- Pass the values and events of the parent component to the grandson component -->
    <!-- <grandson3 v-bind="$attrs" v-on="$listeners"></grandson3> -->
  </div>
</template>
<script>
import grandson from "./grandson.vue";
import grandson2 from "./grandson2.vue";
import grandson3 from "./grandson3.vue";
export default {
  name: "son",
  components: {
    grandson,
    grandson2,
    grandson3
  },
  props:['propsdata']
};
</script>