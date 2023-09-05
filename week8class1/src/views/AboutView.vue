<script setup>
import { ref } from "vue";
import { useMouse } from "../reusables/mouse.js";
import MyModal from "../components/MyModal.vue";

const { x, y } = useMouse();

const vFocus = {
  mounted: (el) => el.focus(),
};

const show = ref(true);
</script>

<template>
  <div class="about">
    <h1>Some Concepts for Week 8</h1>
    Mouse Tracker
    <h1>The Moust Position is at</h1>
    <h2>{{ x }}, {{ y }}</h2>

    <div>
      <input type="text" v-focus />

      <h1>Transition Example</h1>
      <button @click="show = !show">Toggle</button>
      <Transition>
        <p v-if="show">Hello</p>
      </Transition>
    </div>

    <div class="outer">
      <h3>Vue Teleport Example</h3>
      <div>
        <MyModal />
      </div>
    </div>
  </div>
</template>

<style>
/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
