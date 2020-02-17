<template>
    <div class="feature-card">
        <img :src="require(`@/assets/images/features/${image}`)" class="header-img"/>
        <h5 class="feature-title">{{title}}</h5>
        <p class="feature-desc">
            {{desc}}
        </p>
    </div>
</template>
<script>
export default {
    props:['image','title','desc']
}
</script>

<style lang="scss">
@import "@/components/Features/feature.scss";
</style>