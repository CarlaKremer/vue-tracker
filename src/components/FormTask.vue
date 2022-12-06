<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="New task creation form">
        <input
          type="text"
          class="input"
          placeholder="What task do you want to start?"
        />
      </div>
      <div class="column">
        <TimerControl />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TimerControl from "./TimerControl.vue";
export default defineComponent({
  name: "FormTask",
  components: {
    TimerControl,
  },
});
</script>

<style scoped>
::placeholder {
  color: black;
}
input {
  border: 2px solid #ae6378;
  background-color: #eeecec;
}
button {
  margin: 0px 5px 0 5px;
  border: 3px solid #ae6378;
  border-radius: 20px;
  background-color: #eeecec;
}
.box {
  align-items: center;
  background-color: #383b42;
  background-color: #2f3137;
  border-radius: 0px;
}
</style>
