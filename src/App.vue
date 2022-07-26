<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <HelloWorld ref="helloWorld" />
</template>

<script lang="ts">
import { onMounted, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  components: { HelloWorld },
  setup() {
    const helloWorld = ref(null);

    onMounted(() => {
      console.log(helloWorld.value);
    });

    return {
      helloWorld,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
