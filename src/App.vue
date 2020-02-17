<template>
  <div id="app">
    <div class="content">
      <div class="menu-banner-container" id="particles-js">
        <AppNavbar></AppNavbar>
        <vue-particles
        :hoverEffect="false"
        :particleSize= 3
        :clickEffect = "false"
        >
      </vue-particles>
      <AppBanner></AppBanner>
      </div>
      <AppAbout></AppAbout>
      <AppFeature></AppFeature>
      <AppTimeline></AppTimeline>
      <AppStatistic 
      :ChartType="'doughnut'"
      :data = "[1, 1, 1, 1]"
      :labels = "['num1', 'num2', 'num3', 'num4']"
      ></AppStatistic>

      <AppSubscribe></AppSubscribe>


      
    </div>
  </div>
</template>

<script>
import AppNavbar from '@/components/Navbar/navbar';
import AppBanner from '@/components/Banner/banner';
import AppAbout from '@/components/About/about-wrapper';
import AppFeature from '@/components/Features/features-wrapper';
import AppTimeline from '@/components/Timeline/timeline-wrapper';
import AppStatistic from '@/components/custom-statistic/custom';
import AppSubscribe from '@/components/Subscribe/subscribe-wrapper';
//import AppStatistic from '@/components/Statistics/statistic-wrapper';


import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'App',
  components:{
    AppNavbar,
    AppBanner,
    AppAbout,
    AppFeature,
    AppTimeline,
    AppStatistic,
    AppSubscribe
  },
  created(){
    AOS.init();
  }
}
</script>

<style lang="scss">



</style>
