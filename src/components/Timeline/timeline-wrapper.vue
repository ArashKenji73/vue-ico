<template>
    <section id="timeline" data-aos="fade-down">
        <h1 class="main-title">TimeLine</h1>
        <div class="container">
            <div id="cd-timeline">
                <timeline  v-for="(item,i) in timelines" :key="i"
                :title="item.title"
                :content="item.content"
                :date="item.date"
                >
                    
                </timeline>
            </div>
        </div>
    </section>
</template>
<script>
import timeline from '@/components/Timeline/timeline';
export default {
    data(){
        return{
            timelines:[
                {
                    title: 'First',
                    content: 'Working alongside the designer team implementing the designs, also developing custom solutions to address team necessities.',
                    date:'Jan 24'
                },
                {
                    title: 'Second',
                    content: 'Working alongside the designer team implementing the designs, also developing custom solutions to address team necessities.',
                    date:'Jan 24'
                },
                {
                    title: 'Third',
                    content: 'Working alongside the designer team implementing the designs, also developing custom solutions to address team necessities.',
                    date:'Jan 24'
                }
            ]
        }
    },
    components: {
        timeline
    }
}
</script>
<style lang="scss">


#timeline {
    background: $DarkBlue;
    padding: 3rem 0px;
}



#cd-timeline {
    position: relative;
    padding: 2em 0;
    //margin-top: 2em;
    //margin-bottom: 2em;
    &::before {
        content: '';
        position: absolute;
        top: 0;
        left: 25px;
        height: 100%;
        width: 4px;
        background: $Purple;
    }
}


@media only screen and (min-width: 1170px) {

    #cd-timeline::before {
        left: 50%;
        margin-left: -2px;
    }
}
</style>