<template>
  <div id="app" class="main">
    <h1>Parent component</h1>
    <textarea class="content" type="text" v-model="text" />
    <!-- v-model dynamically binds data -->
    <p></p>
    <button @click="send">
      Click to send input data
    </button>
    <!-- Method 1: Central event bus, use the method to pass values with sibling components -->
    <!-- Method 2: provide / inject -->
    <!-- Method 3: $attrs/ $listeners -->
    <son :message="message" :propsdata="propsdata" v-on:grandsonData="grandsonData"></son>
  </div>
</template>

<script>
import son from "./components/son";
// use the event bus
import {bus}from "./main";
export default {
  name: "App",
  components: {
    son
  },
  data() {
    return {
      text: "",
      propsdata: 'The value passed through pros is not on $attrs',
      message: {
        info: ""
      }
    };
  },
  methods: {
    send() {
      this.message.info = this.text;
      bus.$emit("eventBus", this.text);
    },
    // The grandson component passes the value to the parent component
    grandsonData(obj){
        console.log('Get the value of the grandson component: '+obj);
    }
  },

// Method 2: The parent component provides the provide function to pass values to the descendants
// Pass in an object to make provide responsive
    provide(){
      return {
          // Directly passing in a variable value (text here) cannot be responsive, changing the value of the input box will not change the value received by the descendant component
          // fatherTxet: this.text
          //Pass in the message object to achieve responsive development
          fatherTxet: this. message

      }
    }
};
</script>

<style scoped>
.main {
  width: 500px;
  margin: auto;
}
.content {
  width: 250px;
  height: 150px;
  background-color: #ecf2f7;
}
</style>