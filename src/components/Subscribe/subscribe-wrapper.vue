<template>
    <section id="subscribe">
    <div class="container">
        <h1 class="main-title">subscribe</h1>

        <Form></Form>

        <Socials class="subscribe-socials"></Socials>
    </div>
</section>
</template>
<script>
import Form from '@/components/Subscribe/subscribe-form';
import Socials from '@/components/Socials/socials';
export default {
    components:{
        Form,
        Socials
    }
}
</script>
<style lang="scss">
#subscribe {
    padding: 3rem 0px;
}

.subscribe-socials {
    width: 20%;
    margin: 1rem auto;
}

@media (max-width: 576px) {
    .subscribe-socials {
        width: 215px;
    }
}

</style>