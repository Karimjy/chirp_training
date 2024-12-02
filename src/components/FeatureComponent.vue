<template>
  <div class="feature h-full rounded-md p-6">
      <div class="picto">
        <img :src="imageUrl" />
      </div>
      <div class="w-full">
      <div class="title text-black font-bold my-5">{{ title }}</div>
      <div class="description">
        {{ desc }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  image: String,
  title: String,
  desc: String,
});

const imageUrl = computed(() => require(`@/assets/${props.image}`));

</script>

<style lang="scss" scoped>
.feature {
  border: 1px solid #c4c4c4;
  color: #737373;
  font-size: 18px;
  line-height: 29px;
      position: relative;
    overflow: hidden;

  img {
    max-width: 36px;
  }
}
</style>