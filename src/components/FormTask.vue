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
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong>{{ timeElapsed }}</strong>
          </section>
          <button class="button" @click="startCount">
            <span class="icon">
              <i class="fa-solid fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="endCount">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FormTask",
  data() {
    return {
      timeInSeconds: 0,
      counterReference:0
    };
  },
  computed: {
    timeElapsed(): string {
      return new Date(this.timeInSeconds * 1000)
        .toISOString()
        .substring(11, 19);
    },
  },
  methods: {
    startCount() {
      this.counterReference = setInterval(() => {
        this.timeInSeconds += 1;
      }, 1000);
    },
    endCount() {
      clearInterval(this.counterReference)
    },
  },
});
</script>

<style scoped></style>
