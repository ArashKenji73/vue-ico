<template>
<div class="cd-timeline-block">
    <div class="cd-timeline-img"></div>
    <div class="cd-timeline-content">
        <h2>{{title}}</h2>
        <p>{{content}}</p>
        <span class="cd-date">{{date}}</span>
    </div>
</div>
</template>
<script>
export default {
    props:['title','content','date'],
}
</script>
<style lang="scss">
@import "@/components/Timeline/timeline.scss";
</style>