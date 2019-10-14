<template>
  <main id="threeSwiper">
      <!-- swiper -->
          <swiper :options="swiperOption">
            <swiper-slide class="name" v-for="(v,i) in list3">
                <div class="box">
                    <router-link to="">
                        <div class="pic">
                            <img :src="v.img" alt="">
                            <span class="travelType">{{v.type}}</span>
                        </div>
                        <div class="info">
                            <div class="top">
                                <h4 class="mainTitle">{{v.th4}}</h4>
                            </div>
                            <div class="bottom">
                                <span class="price">
                                    <span>¥</span>
                                    <span class="txt">{{v.price}}</span>
                                    <span>起</span>
                                </span>
                                <span class="time">
                                    <em>距结束</em>
                                    <span class="day">5</span>天
                                    <span class="hours">03</span> : 
                                    <span class="minutes">03</span> : 
                                    <span class="senconds">14</span>
                                </span>
                            </div>
                        </div>
                    </router-link>
                </div>
                <span class="distab">享优惠立减</span>
            </swiper-slide>
            <!-- <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide>
            <swiper-slide><img src="../assets/img/tiananmen.jpg" alt=""></swiper-slide> -->
            <!-- <div class="swiper-pagination" slot="pagination"></div> -->
          </swiper>
  </main>
</template>

<script>
export default {
    name:"threeSwiper",
    data(){
        return{
            list3:"",
            swiperOption: {
              slidesPerView: 3,
              spaceBetween: 30,
              pagination: {
                el: '.swiper-pagination',
                clickable: true
              }
            }
        }
    },
    mounted(){
         this.$http.get('./data/table.json')
           .then( (response)=> {
                console.log(response);
                this.list3 = response.data.especialSale
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
                // always executed
            });  
    }
}
</script>

<style scoped>
    .name{
        position: relative;
        left: 0;
        width: 140px !important; 
        margin-left: 15px;
    }
    .name img{
        width: 100%;
    }
    .name .box a{
        color: #333;
        text-decoration: none;
    }
    .box a .pic{
        position: relative;
        width: 100%;
        height: 120px;
        overflow: hidden;
        background: url("../assets/img/vlogo.gif") 50% 50% no-repeat
    }
    .box a .pic .travelType{
        position: absolute;
        top: 0;
        left: 0;
        box-sizing: border-box;
        width: 100%;
        height: 40px;
        padding: 7px 0 0 10px;
        font-size: 12px;
        line-height: 18px;
        color: #fff;
        background: linear-gradient(180deg,rgba(0,0,0,.6) 0,rgba(0,0,0,0) 100%);
    }
    .name .box a .info{
        margin: 5px 0 0;
    }
    .info .top .mainTitle{
        display: -webkit-box;
        height: 34px;
        padding: 0 1px;
        margin-bottom: 0;
        overflow: hidden;
        font-size: 14px;
        font-weight: 400;
        line-height: 17px;
        color: #333;
        text-overflow: ellipsis;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        white-space: normal;
    }
    .info .bottom{
        height: initial;
        margin-top: 10px;
        line-height: initial;
    }
    .info .bottom .price{
        height: initial;
        font-weight: 700;
        line-height: initial;
        color: #ff6257; 
    }
    .info .price span:nth-child(1){
        margin-right: 3px;
        font-size: 12px;
        font-weight: 400;
    }
    .info .price span:nth-child(2){
        font-size: 18px;
        font-weight: 700;
    }
    .info .price span:nth-child(3){
        font-size: 12px;
        font-weight: 400;
        color: #b2b2b2;
    }

    /* 倒计时 */
    .info .bottom .time{
        position: absolute;
        top: 97px;
        left: 0;
        float: right;
        width: 140px;
        height: 23px;
        margin: 0;
        font-size: 11px;
        line-height: 23px;
        color: #fff;
        text-align: center;
        background: rgba(19,20,21,0.6);
    }
    .bottom .time span{
        display: inline-block;
        width: 0.75rem;
        height: 0.975rem;
        background-color: white;
        color: #333;
    }
    .distab{
        position: absolute;
        right: 2px;
        bottom: 2px;
        padding: 0 7px;
        font-size: 10px;
        color: #FF6257;
        background: #FFEDEC;
        border-radius: 4px 4px 4px 0;
    }
</style>