<template>
  <div id="app">
    <!-- Method 1: Event bus (communication between sibling1 and sibling2)-->
     <child1></child1>
     <div style="margin:50px"></div>
     <child2></child2> 

    <!-- Method 2: Son 1 to father, father to son 2 -->
    <!-- <child3 @sibing3click="passclick"></child3>
    <div style="margin: 50px"></div>
    <child4 :mes="passmsg"></child4> -->
  </div>
</template>

<script>
import child1 from "./components/sibling1.vue";
import child2 from "./components/sibling2.vue";
import child3 from "./components/sibling3.vue";
import child4 from "./components/sibling4.vue";
export default {
  name: "App",
  data() {
    return {
      passmsg: "",
    };
  },
  components: {
    child1,
    child2,
    child3,
    child4,
  },
  methods: {
    passclick(data) {
      this.passmsg = data;
      console.log(this.passmsg);
    },
  },
};
</script>

