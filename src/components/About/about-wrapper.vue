<template>
    <section id="about">
        
    <div class="container">
        <AboutBlock v-for="(item,i) in infos" :key="i" 
        :title="item.title"
        :image="item.image"
        :class="{even: i%2 == 0, odd: i%2 == 1}">
           <p slot="content" class="desc">{{infos[0].content}}</p>
           <ul slot="content-list" class="info-list">
                <li v-for="(item,i) in infos[0].list" :key="i">
                    {{item}}
                </li>
           </ul>
        </AboutBlock>
    </div>
    </section>        
</template>
<script>
import AboutBlock from '@/components/About/about';
import $ from "jquery";
export default {
    data(){
        return{
            infos:[
                {
                    title:"Tokenization Benefits",
                    image:"graph-jasmine-b.png",
                    content:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                    list: ['Ut enim ad minim veniam','Ut enim ad minim veniam2','Ut enim ad minim veniam3']
                },

                {
                    title:"Tokenization Benefits",
                    image:"graph-jasmine-c.png",
                    content:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                    list: ['Ut enim ad minim veniam','Ut enim ad minim veniam2','Ut enim ad minim veniam3']
                },
                                {
                    title:"Tokenization Benefits",
                    image:"graph-jasmine-b.png",
                    content:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                    list: ['Ut enim ad minim veniam','Ut enim ad minim veniam2','Ut enim ad minim veniam3']
                },

                {
                    title:"Tokenization Benefits",
                    image:"graph-jasmine-c.png",
                    content:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis unde ex, labore sed! Ut debitis, dolorem nemo velit, est, dolore nostrum et ea alias minima quas nam provident suscipit voluptatem.',
                    list: ['Ut enim ad minim veniam','Ut enim ad minim veniam2','Ut enim ad minim veniam3']
                },

            ]
        }
    },
    components:{
        AboutBlock
    },
    mounted(){
        var infoCount = $('#about .container').children().length;
        for (var i = 1; i <= infoCount; i++) {
            if (i % 2 == 0) {
                //console.log('zooj left' + i);
                $('#about .container .about-block')[i - 1].setAttribute('data-aos', 'fade-right');
            } else {
                //console.log('fard right'+ i);
                $('#about .container .about-block')[i - 1].setAttribute('data-aos', 'fade-left');
            }
        }
    }
}
</script>
<style lang="scss">
    #about {
        overflow-x: hidden;
        background: $DarkBlue;
        .container {
            height: auto;
            padding: 2rem 0px;

        }
    }
</style>