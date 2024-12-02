<template>
  <div class="tweet bg-white rounded-md p-7">
    <div class="head flex justify-between">
      <div class="profil flex">
        <img :src="imageUrl" alt="" />
        <div class="name leading-5 ml-2">
          <div class="fullname text-black font-bold">{{ name }}</div>
          <div class="tag">{{ tag }}</div>
        </div>
      </div>

      <div class="picto mt-1">
        <img src="@/assets/TwitterBlue.svg" alt="" />
      </div>
    </div>
    <div class="desc my-5">
      {{ desc }}
    </div>
    <div class="footer flex justify-between items-center">
      <div class="like flex">
        <img src="@/assets/Like.svg" alt="" />
        <p class="ml-2">{{ like }}</p>
      </div>
      <div class="date">{{ date }}</div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  profile: String,
  name: String,
  tag: String,
  desc: String,
  like: String,
  date: String,
});

const imageUrl = computed(() => require(`@/assets/${props.profile}`));
</script>

<style lang="scss" scoped>
.tweet {
  color: #737373;
  .name {
    .fullname {
      font-size: 18px;
    }
    .tag {
      color: #737373;
      font-size: 14px;
    }
  }
}
</style>