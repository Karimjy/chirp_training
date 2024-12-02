<template>
  <button
    class="text-white font-bold flex items-center justify-center rounded"
    :class="[fullwidth ? 'w-full' : 'fix-width']"
  >
    <img src="@/assets/Twitter.svg" alt="" />
    <p class="ml-3">Sign in with Twitter</p>
  </button>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  fullwidth: {
    type: Boolean,
    default: false,
  },
});

</script>


<style lang="scss" scoped>
button {
  background-color: #1da1f2;
  height: 55px;
}

button.fix-width {
  width: 254px;
}

@media (max-width: 768px) {
  button.fix-width {
    width: 100%;
  }
}
</style>