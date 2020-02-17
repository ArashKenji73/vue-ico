<template>
<nav class="fixed" id="navbar">
    <div class="container">
        <div class="navbar-header">
            <a class="logo" href="#">
                <img :src="require(`@/assets/images/menu/logo-big.png`)"/>
            </a>
            <button id="toggle-menu" @click="toggleMenu">
                <i class="fas fa-bars"></i>
            </button>
        </div>
        <div class="main-menu">
            <a class="item" href="#">Home</a>
            <a class="item" href="#">Features</a>
            <a class="item" href="#">Pricing</a>
        </div>
    </div>
</nav>  
</template>
<script>
import $ from "jquery";
export default {
    methods:{
        toggleMenu(){
            $('.main-menu').slideToggle();
        }
    }
}
</script>
<style lang="scss">
@import "@/components/Navbar/navbar.scss";
</style>