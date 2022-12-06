<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-1">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <FormTask />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar.vue";
import FormTask from "./components/FormTask.vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    FormTask,
  },
});
</script>

<style>
main {
  background-color: #2f3137;
  background-color: #1c1d22;
}
</style>
