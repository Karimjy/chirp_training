<template>
    <div class="flex justify-between items-center">
        <div class="logo italic">
            Chirp.
        </div>
        <div class="burger md:hidden">
            <img src="@/assets/HamburgerMenu.svg" alt="">
        </div>
        <nav class="hidden md:flex items-center gap-7 w-8/12">
            <p><a href="/">Home</a></p>
            <p><a href="/#pricing" @click="scrollTo()" class="cursor-pointer">Pricing</a></p>
            <p>FAQ</p>
            <TwitterButtonComponent />
        </nav>
    </div>
</template>

<script setup>
import { defineEmits } from "vue";
import TwitterButtonComponent from "@/components/TwitterButtonComponent.vue";

const emits = defineEmits(['scrollTo'])

function scrollTo(){
  emits('scrollTo')
}

</script>


<style lang="scss" scoped>
    div{
        .logo{
            font-size: 24px;
            color: #3180f5;
            font-weight: 700;  
        }

        nav{
            font-size: 16px;
            max-width: 478px;
        }
    }
</style>