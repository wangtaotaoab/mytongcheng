<template>
  <main id="home">
      <vheader></vheader>
      <vbanner></vbanner>
      <vbignav></vbignav>
      <vtickets></vtickets>
      <vdownload></vdownload>
      <vrecommend></vrecommend>
      <vadvantage></vadvantage>
      <vindexfooter></vindexfooter>
  </main>
</template>

<script>
import vheader from '../component/vheader.vue'
import vbanner from '../component/banner.vue'
import vbignav from '../component/vbignav.vue'
import vtickets from '../component/tickets.vue'
import vdownload from '../component/downloadapp.vue'
import vrecommend from '../component/recommend.vue'
import vadvantage from '../component/advantage.vue'
import vindexfooter from '../component/indexfooter.vue'
export default {
    name:'home',
    components:{
        vheader,
        vbanner,
        vbignav,
        vtickets,
        vdownload,
        vrecommend,
        vadvantage,
        vindexfooter
    }
}
</script>

<style scoped>
    body{
        background: #f0f4f5;
    }
</style>