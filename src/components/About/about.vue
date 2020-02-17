<template>
<div class="about-block">
    <div class="info">
        <h4 class="title">
            {{title}}
        </h4>
        <slot name="content"></slot>
        <slot name="content-list"></slot>
    </div>
    <div class="image">
        <img :src="require(`@/assets/images/info/${image}`)"/>
    </div>
</div>
    
</template>
<script>
export default {
    props:['title','image']
}
</script>

<style lang="scss">
@import "@/components/About/about.scss";
</style>