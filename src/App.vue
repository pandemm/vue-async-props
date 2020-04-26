<template>
  <div id="app">
    <b-card>
      This sandbox teaches you how to use async props in Vue.
      Async props are data that is fetched from an API
      and then passed as props to a child component.
      In this example we have an API call, that returns us
      the string "API result"
    </b-card>
    <Props :msg="prop"></Props>
    <Computed :msg="prop"></Computed>
    <Watch :msg="prop"></Watch>
    <LifecycleHooks :msg="prop"></LifecycleHooks>
  </div>
</template>

<script>
import Computed from "./components/Computed";
import Watch from "./components/Watch";
import LifecycleHooks from "./components/LifecycleHooks";
import Props from "./components/Props";

export default {
  name: "App",
  components: {
    Computed,
    Watch,
    LifecycleHooks,
    Props
  },
  data() {
    return {
      prop: "undefined"
    };
  },
  // Simulates an API call.
  // After a second the prop will be assigned a velue
  created() {
    setTimeout(() => (this.prop = "API result"), 1000);
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
