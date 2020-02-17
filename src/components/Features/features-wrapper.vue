<template>
    <section id="features" data-aos="fade-up">
        <div class="container">
            <h1 class="main-title">features</h1>
            <div class="features-wrapper">

                <Appfeature  v-for="(item,i) in features" :key="i"
                :title="item.title"
                :image="item.image"
                :desc="item.desc"
                >
                </Appfeature>
            </div>
        </div>
    </section>    
</template>
<script>
import Appfeature from '@/components/Features/feature';
export default {
    data(){
        return{
            features:[
                {
                    image:"icon-a.png",
                    title:"Ultra Fast and Secure",
                    desc:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                },
                {
                    image:"icon-b.png",
                    title:"Ultra Fast and Secure",
                    desc:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                },
                {
                    image:"icon-c.png",
                    title:"Ultra Fast and Secure",
                    desc:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                },
                {
                    image:"icon-b.png",
                    title:"Ultra Fast and Secure",
                    desc:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                },
            ]
        }
    },
    components:{
        Appfeature
    }
    
}
</script>
<style lang="scss">

$featuresBG : #00031d;
#features {
    background: $featuresBG;

    .container {
        padding: 3rem 0px;
        .features-wrapper {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            &::after {
                content: '';
                width: 30%;
            }
        }
    }
}

@media (max-width: 576px) {
    #features {
        .container {
            padding-left: 15px;
            padding-right: 15px;
            padding-bottom: 0;
            .features-wrapper {
                flex-direction: column;
            }
        }
    }
}
</style>