<template>
  <main id="jingnei">
      <div class="header">
        <div class="titlebar">
          <span class="font" @click="backgohome()"><i class="iconfont icon-jiantou-copy"></i></span>
          <div class="search">
            <router-link to="">
              <span>广州</span>
              <i></i>
            </router-link>
            <router-link to="">
              <i></i>
              <span>目的地/关键词</span>
            </router-link>
          </div>
          <span class="kefu">
            <i class="iconfont icon-kefu"></i>
          </span>
          <span class="more" @click="change()">
              <i class="iconfont icon-shenglvehao"></i>
          </span>
          <div class="head-menu"  v-show="show" >
              <router-link to='/home'>
                  <i></i><span>首页</span>
              </router-link>
              <router-link to='/my'>
                  <i></i><span>我的同程</span>
              </router-link>
              <router-link to='/login'>
                  <i></i><span>登录/注册</span>
              </router-link>
          </div>
        </div>
      </div>
      <div class="banner">
        <swiper :options="swiperOption">
            <!-- <swiper-slide><img :src="list[0].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[1].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[2].img" alt=""></swiper-slide>
            <swiper-slide><img :src="list[3].img" alt=""></swiper-slide> -->
            <swiper-slide v-for="(v,i) in list"><img :src="v.img"></swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </div>
      <div class="table">
        <ul class="tableUl">
          <li v-for="(v,i) in list1" @click="back(i)">
            <span>{{v.title}}</span>
          </li>
        </ul>
        <div class="destCont">
          <ul v-for="(v,i) in list2"  v-if="i==temp">
            <li v-for="(val,j) in v.a">
              <router-link to="">
                <span>{{val.title}}</span>
              </router-link>
            </li>
            <li>
              <router-link to="">
                更多
              </router-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="saleArea">
        <div class="saleHead">
          <span>特卖汇</span>
          <router-link to=''>
            更多特卖
            <em></em>
          </router-link>
        </div>
        <div class="productCont">
          <vswiper></vswiper>
        </div>
        <div class="themetour">
            <h1>
              <span>主题游</span>
            </h1>
            <div class="container">
              <ul class="containerUl">
                <li>
                  <router-link to=''>
                    <img src="../assets/img/bamayou.jpg" alt="">
                  </router-link>
                </li>
                <li>
                  <router-link to=''>
                    <img src="../assets/img/huwaiyou.jpg" alt="">
                  </router-link>
                </li>
                <li>
                  <router-link to=''>
                    <img src="../assets/img/tongchengzhuanxian.jpg" alt="">
                  </router-link>
                </li>
                <li>
                  <router-link to=''>
                    <img src="../assets/img/qinziyou.jpg" alt="">
                  </router-link>
                </li>
              </ul>
            </div>
        </div>
        <div class="productArea">
          <h3>同程热推</h3>
          <div class="product-table">
            <ul>
              <li v-for="(v,i) in list3">{{v.title}}</li>
            </ul>
          </div>
          <div class="procont">
            <div class="productlist">
              <router-link :to="'/particulars/'+v.id" v-for="(v,i) in list4">
                <div class="listPic">
                    <img :src="v.img" alt="">
                    <span class="transtype">{{v.type}}</span>
                    <div class="price">￥<em>{{v.price}}</em>起</div>
                    <div class="pic-btm">
                      <div class="pic-btm-txt">
                        <span class="commentnum">{{v.commentNum}}</span>
                        <span class="satisfition">{{v.satisfaction}}</span>
                      </div>
                    </div>
                </div>
                <div class="listInfo">
                  <p class="mainTitle">{{v.mainTitle}}</p>
                  <p class="subTitle">{{v.describe}}</p>
                  <div class="marks">
                    <span class="tczxtag">{{v.tag0}}</span>
                    <span class="tag">{{v.tag1}}</span>
                    <span class="tag">{{v.tag2}}</span>
                    <span class="tag">{{v.tag3}}</span>
                    <span class="tag">{{v.tag4}}</span>
                  </div>
                </div>
              </router-link>
            </div>
            <div class="abtest-more">
              <router-link to="">
                查看更多
              </router-link>
            </div>
          </div>
        </div>
        <div class="bottomArea">
          <div class="bottomtext"></div>
        </div>
        <div class="gotop"></div>
        <div class="chat">
          <router-link to=""></router-link>
        </div>
      </div>
  </main>
</template>

<script>
import vswiper from '../component/threeSwiper.vue'
export default {
    name:"jingnei",
    data(){
        return{
            list:"",
            list1:"",
            list2:"",
            list3:"",
            list4:"",
            temp:0,
            show:false,
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
       this.$http.get('./data/table.json')
           .then( (response)=> {
                console.log(response);
                this.list = response.data.list1
                this.list1 = response.data.top
                this.list2 = response.data.tableList1
                this.list3 = response.data.address
                this.list4 = response.data.retui
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
              
            })
    },
    methods:{
      backgohome(){
        this.$router.go(-1);
      },
      change(){
          this.show = !this.show
      },
      back(i){
        var temp;
					this.temp=i;
					console.log(temp)
      }
    },
    components:{
      vswiper
    }
}

$(function(){
	$(window).scroll(function(){
		var h = $(window).scrollTop();
		// console.log(h);
		if(h>200){
      $(".header .titlebar .font i").css('color','#333');
      $(".titlebar .kefu i").css('color','#333');
      $(".titlebar .more i").css('color','#333');
      $('.header').css("background-color",'white');
      $('.titlebar .search').css("background-color",'#f3f4f5')
		}else{
      $(".header .titlebar .font i").css('color','white');
      $(".titlebar .kefu i").css('color','white');
      $(".titlebar .more i").css('color','white');
      $('.header').css("background-color",'transparent');
      $('.titlebar .search').css("background-color",'rgba(255,255,255,.95)')
    }
		
  })
  
  $(".table .tableUl li:nth-child(1)").children("span").addClass('tableshow');
  $(".table .tableUl li").click(function(){
    $(this).children("span").addClass('tableshow').parent("li").siblings().children("span").removeClass("tableshow");
  })

  $(".gotop").click(function(){
		// var h = $(".siteNav").offset().top; 
		$("html,body").animate({"scrollTop":0},500);
	})
})

</script>

<style scoped>
  .header{
    position: fixed;
    top: 0;
    z-index: 100;
    width: 100%;
    max-width: 640px;
    height: 44px;
  }
  .header .titlebar{
    position: absolute;
    top: 0px;
    right: 14px;
    left: 14px;
    display: flex;
    display: -webkit-flex;
    height: 30px;
    padding: 7px 0;
  }

  .swiper-wrapper{
    background-color: rebeccapurple;
    height: 100px;
  }
  .swiper-container{
        width: 100%;
  }
  .swiper-slide img{
      width: 100%;
  }
  /* 字体图标 */
  .titlebar .font i{
    color: white;
    font-size: 20px;
  }
  
  .search{
    margin-left: 0.5rem;
    flex-grow: 1;
    height: 30px;
    overflow: hidden;
    font-size: 14px;
    line-height: 30px;
    white-space: nowrap;
    background: rgba(255,255,255,.95);
    border-radius: 15px;
  }
  .search a:nth-child(1){
    padding-right: 18px;
    color: #23beae;
    position: relative;
    overflow: hidden;
    border-right: none;
    text-decoration: none;
  }
  .search a:nth-child(1) span{
    float: left;
    max-width: 43px;
    margin-left: 15px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .search a:nth-child(1) i{
    position: relative;
    top: 0;
    left: 6px;
    display: inline-block;
    width: 10px;
    height: 10px;
    background: url('../assets/img/tongindex.png') center no-repeat;
    background-size: 100%;
  }
  .search a:nth-child(1)::after{
    position: absolute;
    top: 0;
    right: 0;
    width: 1px;
    height: 100%;
    content: "";
    background: #dcdcdc;
  }

  .search a:nth-child(2) i{
    display: inline-block;
    width: 12px;
    height: 12px;
    margin-right: 6px;
    margin-bottom: -1px;
    background: url('../assets/img/search.png') center no-repeat;
    background-size: 100%;
  }
  .search a:nth-child(2){
    text-decoration: none;
    display: inline-block;
    width: 67%;
    height: 30px;
    margin-left: 8px;
    color: #999;
    text-align: left;
  }

  /* 客服 */
  .titlebar .kefu{
    display: inline-block;
    width: 20px;
    height: 30px;
    margin: 0 5px 0 14px;
    line-height: 28px;
    text-align: center;
  }
  .titlebar .kefu i{
    font-size: 26px;
    color: #fff;
  }
  /* 更多 */
  .titlebar .more{
    display: inline-block;
    width: 20px;
    height: 30px;
    margin-left: 5px;
    line-height: 28px;
    text-align: center;
    position: static;
    /* padding-left: 0.75rem; */
    top: 0;
    right: 0;
  }
  .titlebar .more i{
    font-size: 26px;
    color: #fff;
  }
  /* 弹出框 */
  .head-menu{
        position: absolute;
        right: 0px;
        border-radius: 5px;
        background: #f7f7f7;
        font-size: 18px;
        -webkit-transition: all 0.2s ease-in-out;
        transition: all 0.2s linear;
        top: 53px;
        z-index: 1;
    }
    .head-menu::before{
        content: "";
        position: absolute;
        top: -9px;
        right: 8px;
        height: 0;
        border-style: solid;
        border-color: #434950 transparent;
        border-width: 0 9px 9px;
    }
    .head-menu a{
        display: block;
        line-height: 44px;
        width: 132px;
        background: #434950;
        color: #ccc;
        text-decoration: none;
    }
    .head-menu a i{
        display: inline-block;
        width: 20px;
        height: 20px;
        margin: 12px 6px 0 12px;
        background: url('../assets/img/z7DRnw.png')no-repeat;
        background-size: 20px 80px;
    }
    .head-menu a:nth-child(1) i{
        background-position: 0 2px;
    }
    .head-menu a:nth-child(2) i{
        background-position: 0 -18px;
    }
    .head-menu a:nth-child(3) i{
        background-position: -1px -38px;
    }

    /* table栏 */
    .table{
      margin-bottom: 10px;
      font-size: 14px;
      color: #333;
      background: #fff;
    }
    .tableUl{
      height: 43px;
      padding: 0 10px;
      position: relative;
      overflow: hidden;
      border-bottom: none;
    }
    .tableUl li{
      float: left;
      width: 25%;
      height: 40px;
      line-height: 40px;
      color: #666;
      text-align: center;
      position: relative;
    }
    .tableUl li span{
      width: 74px;
    }
    .tableUl li .tableshow{
      color: #23beae;
    }

    .destCont{
      padding: 13px 10px 0;
    }
    .destCont ul li{
      position: relative;
      box-sizing: border-box;
      float: left;
      width: 23%;
      height: 30px;
      margin-right: 2%;
      margin-bottom: 13px;
      line-height: 30px;
      text-align: center;
      background: #fff;
      border: 1px solid #e4e4e4;
    }
    .destCont ul li a{
      display: inline-block;
      width: 100%;
      height: 100%;
      background: 0 0;
      color: #333;
      text-decoration: none;
    }

    /* 特卖汇 */
    .saleArea{
      clear: both;
      padding-top: 15px;
      margin-top: 10px;
      background: #fff;
    }
    .saleArea .saleHead{
      height: 24px;
      line-height: 24px;
    }
    .saleArea .saleHead span{
      margin: 0 0 0 15px;
      font-size: 18px;
      font-weight: 700;
      color: #333;
    }
    .saleHead a{
      position: relative;
      float: right;
      padding-right: 2rem;
      font-size: 12px;
      color: #666;
      text-decoration: none;
    }
    .saleHead a em{
      position: absolute;
      top: 7px;
      right: 17px;
      width: 10px;
      height: 10px;
      font-size: 13px;
      background: url("../assets/img/turnleftArrow.png");
      background-size: 50%;
    }

    .productCont{
      box-sizing: border-box;
      height: 205px;
      padding: 0 0 15px;
      margin-top: 10px;
      position: relative;
      overflow: hidden;
    }

    /* 主体游 */
    .themetour{
      margin-top: 10px;
      background: #fff;
      padding: 15px 0 0;
    }
    .themetour h1{
      padding-bottom: 10px;
      margin-left: 15px;
      font-size: 18px;
      font-weight: 700;
      line-height: 30px;
      color: #333;
    }
    .container{
      height: 105px;
      overflow: hidden;
      white-space: nowrap;
    }
    .containerUl{
      height: 180px;
      letter-spacing: -4px;
      position: relative;
      box-sizing: border-box;
      display: block;
      width: 100%;
      padding-right: 10px;
      overflow: scroll;
      white-space: nowrap;
      background-color: #fff;
    }
    .containerUl li{
      width: 107px;
      height: 90px;
      margin-left: 15px;
      position: relative;
      display: inline-block;
    }
    .containerUl li img{
      width: 100%;
    }

    /* 同程热推 */
    .productArea{
      margin-top: 10px;
      background: #fff;
    }
    .productArea>h3{
      height: 42px;
      font-size: 16px;
      line-height: 42px;
      color: #23beae;
      text-align: center;
      position: relative;
      overflow: hidden;
      border-bottom: none;
    }

    .productArea .product-table{
      height: 30px;
      padding: 10px 0;
        overflow-x: scroll;
        overflow-y: hidden;
        /*解决ios上滑动不流畅*/
        -webkit-overflow-scrolling: touch;
        /*纵向超出部分将会隐藏，即滚动条部分被挤出可视区域*/
        padding-bottom: 20px;
    }
    .product-table ul{
      height: 30px;
      padding: 0 10px;
      position: relative;
      box-sizing: border-box;
      display: block;
      width: 100%;
      padding-right: 10px;
      /* overflow: scroll; */
      /* overflow: hidden; */
      overflow-x: scroll;
        overflow-y: hidden;
      white-space: nowrap;
      background-color: #fff;
    }
    .product-table ul li{
      box-sizing: border-box;
      width: 78px;
      height: 29px;
      margin-right: 9px;
      font-size: 12px;
      line-height: 29px;
      color: #666;
      text-align: center;
      border: 1px solid #ededed;
      border-radius: 1px;
      position: relative;
      display: inline-block;
    }
    .product-table ul .active{
      color: #23beae;
      background: #d3f2ef;
      border: 1px solid #23beae;
    }

    /* 同程热推内容分页 */
    .productlist{
      border-bottom: 1px solid #dccddc;
    }
    .productlist a{
      background: 0 0;
      color: #333;
      text-decoration: none;
      display: block;
    }
    .listPic{
      position: relative;
      width: 100%;
      height: 0;
      padding-bottom: 50%;
      background: url('../assets/img/vlogo.gif') 50% 50% no-repeat;
    }
    .listPic>img{
      width: 100%;
    }
    .listPic .transtype{
      position: absolute;
      top: 10px;
      left: 10px;
      padding: 0 8px;
      font-size: 10px;
      line-height: 18px;
      color: #fff;
      background: rgba(51,51,51,.6);
      border-radius: 18px;
    }
    .listPic .price{
      position: absolute;
      right: 0;
      bottom: 9px;
      z-index: 99;
      min-width: 95px;
      height: 33px;
      font-size: 12px;
      line-height: 33px;
      color: #fff;
      text-align: center;
      background: #333;
    }
    .listPic .price em{
      font-style: normal;
      font-size: 18px;
    }
    .listPic .pic-btm{
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 40px;
      color: #fff;
      background: -webkit-linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.5));
    }
    .listPic .pic-btm .pic-btm-txt{
      position: absolute;
      bottom: 9px;
      left: 0;
      padding: 0 16px;
      font-size: 0;
      line-height: 1;
    }
    .pic-btm .pic-btm-txt span{
      margin-right: 20px;
      font-size: 0.48rem;
    }
    .productlist a .listInfo{
      padding: 0px 10px;
    }
    .listInfo .mainTitle{
      padding: 0 1px;
      margin: 8px 0 6px;
      overflow: hidden;
      font-size: 16px;
      color: #333;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .listInfo .subTitle{
      padding: 0 1px;
      margin-bottom: 10px;
      overflow: hidden;
      font-size: 12px;
      line-height: 1.2;
      color: #999;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .listInfo .marks{
      width: auto;
      height: 15px;
      margin-bottom: 13px;
      overflow: hidden;
      font-size: 0;
    }
    .listInfo .marks span{
      display: inline-block;
      height: 15px;
      padding: 0 5px;
      margin-right: 5px;
      font-size: 9px;
      line-height: 13px;
    }
    .listInfo .marks .tag{
      box-sizing: border-box;
      color: #ff5028;
      border: 1px solid #ffa793;
      border-radius: 1px;
    }
    .listInfo .marks .tczxtag{
      box-sizing: border-box;
      float: left;
      color: #00c6c4;
      border: 1px solid #7fe2e1;
      border-radius: 1px;
    }

    /* 查看更多 */
    .abtest-more a{
      text-decoration: none;
      display: inline-block;
      width: 100%;
      height: 44px;
      font-size: 14px;
      line-height: 44px;
      color: #999;
      text-align: center;
    }

    /* 脚注 */
    .bottomArea{
      background: #f2f4f7;
    }
    .bottomArea .bottomtext{
      width: 100%;
    height: 103px;
    background: url('../assets/img/index_bottomtext-065ad4509d.jpg') center no-repeat;
    background-size: 375px 103px;
    }

    /* 返回顶部 */
    .gotop{
      position: fixed;
      right: 15px;
      bottom: 15px;
      width: 50px;
      height: 50px;
      background: url('../assets/img/icon-gotop-ffb541d4d1.png') no-repeat;
      background-size: contain;
    }

    /* 客服 */
    .chat a{
      position: fixed;
      right: 15px;
      bottom: 80px;
      display: block;
      width: 50px;
      height: 50px;
      background: url(https://pic5.40017.cn/04/002/bc/be/rBTJUl1I7RGAB7uAAAATtBOCAHE978.png) no-repeat;
      background-size: contain;
      color: #333;
      text-decoration: none;
    }
</style>