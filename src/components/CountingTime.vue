<template>
  <section class="timer">
    <strong class="timer">{{ timeElapsed }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "CountingTime",
  props: {
    timeInSeconds: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    timeElapsed(): string {
      return new Date(this.timeInSeconds * 1000)
        .toISOString()
        .substring(11, 19);
    },
  },
});
</script>

<style scoped>
.timer {
  font-size: 24px;
  align-self: center;
  color: whitesmoke;
}
</style>
