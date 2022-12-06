<template>
  <div class="is-flex is-align-items-center is-justify-content-space-evenly">
    <CountingTime :timeInSeconds="timeInSeconds" />
    <div>
      <button class="button" @click="startCount" :disabled="timerIsCounting">
        <span class="icon" style="color: #ae6378">
          <i class="fa-solid fa-play"></i>
        </span>
      </button>
      <button class="button" @click="endCount" :disabled="!timerIsCounting">
        <span class="icon" style="color: #ae6378">
          <i class="fas fa-stop"></i>
        </span>
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CountingTime from "./CountingTime.vue";

export default defineComponent({
  name: "TimerControl",
  components: {
    CountingTime,
  },
  data() {
    return {
      timeInSeconds: 0,
      counterReference: 0,
      timerIsCounting: false,
    };
  },
  methods: {
    startCount() {
      this.timerIsCounting = true;
      this.counterReference = setInterval(() => {
        this.timeInSeconds += 1;
      }, 1000);
    },
    endCount() {
      this.timerIsCounting = false;
      clearInterval(this.counterReference);
    },
  },
});
</script>

<style scoped>
button {
  border: 3px solid #ae6378;
  background-color: #eeecec;
  margin: 0px 5px 0 5px;
  border-radius: 20px;
}
</style>
