<template>
  <header>
    <h1></h1>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "SideBar",
});
</script>

<style scoped>
header {
  background: #2f3137;
  background: #ae63789c;
  width: 100%;
  height: 100vh;
  padding: 1rem;
}
/* mobile: */
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
