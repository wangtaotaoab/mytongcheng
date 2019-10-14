<template>
    <div  id="banner" class="banner">
        <swiper :options="swiperOption">
            <!-- <swiper-slide><img :src="list[0].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[1].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[2].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[3].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[4].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[5].img" alt=""></swiper-slide> -->
            <swiper-slide v-for="(v,i) in list"><img :src="v.img"></swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
    name:'banner',
    data(){
        return{
            list:"",
            swiperOption: {
                slidesPerView: 1,
                spaceBetween: 30,
                centeredSlides: true,
                loop: true,
                autoplay: {
                    delay: 2500,
                    disableOnInteraction: false
                },
                pagination: {
                    el: '.swiper-pagination',
                    clickable: true
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                }
            }
        }
    },
    mounted(){
       this.$http.get('./data/indexBanner.json')
           .then( (response)=> {
                // console.log(response);
                this.list = response.data.list
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
    .banner{
        /* height: 95px;
        background-color: gold; */
    }
    .swiper-container{
        width: 100%;
    }
    .swiper-slide img{
        width: 100%;
    }
</style>