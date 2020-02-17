<template>
<div class="banner">
<div class="container">
    <div class="header-txt-wrapper" data-aos="fade-right">
        <h1 class="header">
            Powering Data for the new equity blockchain
        </h1>
        <p class="desc">
            Global decentralize network to buy and sell shares
        </p>

        <div class="cta-wrapper">
            <button class="btn cta-btn">
                sign up
            </button>

            <button class="btn cta-btn">
                token distr
            </button>
        </div>
        <Socials class="socials-banners"></Socials>
    </div>

    <div class="banner-img" data-aos="fade-left">
        <img :src="require(`@/assets/images/banner/banner.png`)"/>
    </div>
</div>
</div>
</template>
<script>
import Socials from '@/components/Socials/socials'
export default {
    components:{
        Socials
    }
}
</script>
<style lang="scss">
@import "@/components/Banner/banner.scss";
</style>