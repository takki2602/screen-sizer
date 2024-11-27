<script setup>
import { ref, onMounted } from "vue";

const outerSize = ref(window.outerWidth + " x " + window.outerHeight);
const innerSize = ref(window.innerWidth + " x " + window.innerHeight);

onMounted(() => {
  window.addEventListener("resize", () => {
    outerSize.value = window.outerWidth + " x " + window.outerHeight;
    innerSize.value = window.innerWidth + " x " + window.innerHeight;
  });

  setInterval(() => {
    outerSize.value = window.outerWidth + " x " + window.outerHeight;
    innerSize.value = window.innerWidth + " x " + window.innerHeight;
  }, 100);
});
</script>

<template>
  <div>
    <div class="card">
      <h1>Outer Size: {{ outerSize }}</h1>
      <h1>Inner Size: {{ innerSize }}</h1>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
