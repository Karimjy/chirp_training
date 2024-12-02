<template>
    <footer>
        <div class="flex flex-col py-7 md:flex-row md:items-center md:justify-between w-full">
        <div class="logo italic mb-4 md:mb-0">
            Chirp.
        </div>
        <div class="links">
            <ul class="flex">
                <li>
                    <img src="@/assets/TwitterBlack.svg" alt="">
                </li>
                <li>Privacy Policy</li>
                <li>Terms of Use</li>
            </ul>
        </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
    footer{
        background-color: #d7f5f5;
        .logo{
            font-size: 24px;
            color: #3180f5;
            font-weight: 700;  
        }

        ul li:not(li:first-child){
            margin-left: 1em;
        }
    }
</style>