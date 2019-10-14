<template>
  <main id="my">
      <div class="top">
          <span class="back" @click="back()"></span>
          <h2>我的同程</h2>
          <span class="btnTopRight" @click="change()">
              <i></i>
              <i></i>
              <i></i>
          </span>
          <div class="head-menu"  v-show="show" >
              <router-link to=''>
                  <i></i><span>首页</span>
              </router-link>
              <router-link to=''>
                  <i></i><span>我的同程</span>
              </router-link>
              <router-link to=''>
                  <i></i><span>登录/注册</span>
              </router-link>
          </div>
      </div>
      <div class="logo">
          <router-link to='/login'>
              <span class="leftlogo">
                   <img src="../assets/img/logo.png" alt="">
              </span>
              <span>
                  登录/注册
              </span>
              <span>
                  <img src="../assets/img/5WpEc4.png" alt="">
              </span>
              <span>
                  <img src="../assets/img/turnright2.png" alt="">
              </span>
          </router-link>
      </div>
      <div class="navBlock">
          <div class="allDing">
              <div>
                  <span></span>
                  <h4>
                      <router-link to=''>
                          全部订单
                      </router-link>
                  </h4>
                  <span></span>
              </div>
          </div>
          <div class="personinfo">
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          奖金
                      </router-link>
                  </h4>
                  <span></span>
              </div>
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          立返
                      </router-link>
                  </h4>
                  <span></span>
              </div>
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          红包
                      </router-link>
                  </h4>
                  <span></span>
              </div>
          </div>
          <div class="personinfo">
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          常用信息
                      </router-link>
                  </h4>
                  <span></span>
              </div>
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          我的发票
                      </router-link>
                  </h4>
                  <span></span>
              </div>
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          我的收藏
                      </router-link>
                  </h4>
                  <span></span>
              </div>
              <div class="bg_gray_d">
                  <span></span>
                  <h4>
                      <router-link to=''>
                          关于同程
                      </router-link>
                  </h4>
                  <span></span>
              </div>
          </div>
      </div>
      <div class="footer">
          <div class="footerNav">
              <router-link to=''>客服电话</router-link>
              <router-link to=''>下载客户端</router-link>
              <router-link to=''>关于同程</router-link>
              <router-link to=''>电脑版</router-link>
          </div>
          <p>©2019同程旅游</p>
      </div>
  </main>
</template>

<script>
export default {
    name:'my',
    data(){
        return{
            show:false
        }
    },
    methods:{
        back(){
            this.$router.go(-1)
        },
        change(){
            this.show = !this.show
        }
    }
}
</script>
  
<style>
    html{
        background: #f0f4f5;
    }
    body{
        background: #f0f4f5;
    }
    .top{
        width: 100%;
        background-color: white;
        position: relative;
    }
    .back{
        display: block;
        height: 44px;
        width: 44px;
        position: absolute;
        left: 0;
        top: 0;
    }
    .back::before{
        content: '';
        display: block;
        width: 18px;
        height: 15px;
        margin: 16px 0 0 15px;
        background: url("../assets/img/return.png") no-repeat;
        background-size: contain;
    }
    .top h2{
        line-height: 44px;
        font-size: 18px;
        padding: 0 88px;
        text-align: center;
        font-weight: 400;
        font-weight: 700;
        margin: 0 auto;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        box-sizing: border-box;
    }
    .btnTopRight{
        position: absolute;
        top: 0;
        right: 0;
        line-height: 44px;
        padding: 0 15px 0 10px;
    }
    .btnTopRight i{
        display: inline-block;
        width: 4px;
        height: 4px;
        background: #23beae;
        border-radius: 50%;
        vertical-align: middle;
    }
    .head-menu{
        position: absolute;
        right: 5px;
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
    .logo{
        max-width: 640px;
        min-width: 320px;
        height: 100px;
        background-size: 100%;
        position: relative;
        margin: 0 auto;
        background-color: #00c8b3;
    }
    .leftlogo{
        width: 3.2rem;
        height: 3.2rem;
        display: inline-block;
        margin: 1rem 0 0 1rem;
    }
    .leftlogo img{
        width: 100%;
    }
    .logo a{
        text-decoration: none;
        color: white;
        font-size: 1.1rem;
    }
    .logo a span:nth-child(2){
        position:relative;
        top: -1rem;
        left: 0.2rem;
    }
    .logo a span:nth-child(3){
        display: inline-block;
        width: 100px;
        height: 54px;
        margin-left: 2.5rem;
    }
    .logo a span:nth-child(3) img{
        width: 100%;
        height: 100%;
    }
    .logo a span:nth-child(4){
        display: inline-block;
        width: 7px;
        height: 13px;
        position: absolute;
        right: 15px;
        top: 42px;
    }
    .logo a span:nth-child(4) img{
        width: 100%;
        height: 100%;
    }
    .navBlock{
        margin: 0 auto;
        min-height: 203px;
        padding: 0 0 18px 0;
        background-color: #edf0f5;
    }
    .allDing{
        margin-bottom: 0.625rem;
        background-color: white;
    }
    .allDing>div{
        background-color: #fff;
        color: #333;
        font-size: 30px;
        position: relative;
    }
    .allDing>div span:nth-child(1){
        display: inline-block;
        margin-top: 12px;
        position: absolute;
        width: 18px;
        height: 21px;
        margin-left: 11px;
        background-size: contain;
        left: 4px;
        background: url("../assets/img/dingdan.png") no-repeat;
        background-size: 1rem;
    }
    .allDing>div h4{
        line-height: 26px;
        text-align: left;
        color: #333;
        padding: 8px 0 9px 47px;
        font-size: 16px;
        cursor: default;
    }
    .allDing>div h4 a{
        text-decoration: none;
        color: #333;
    }
    .allDing>div span:nth-child(3){
        display: inline-block;
        width: 7px;
        height: 13px;
        position: absolute;
        right: 15px;
        top: 14px;
        background: url('../assets/img/turenright1.png') no-repeat center;
        background-size: contain;
    }
    .personinfo{
        margin-bottom: 10px;
    }
    .bg_gray_d {
        background-color: #fff;
        color: #333;
        font-size: 30px;
        position: relative;
    }
    .bg_gray_d span:nth-child(1){
        display: inline-block;
        margin-top: 12px;
        position: absolute;
        width: 18px;
        height: 21px;
        margin-left: 11px;
        /* background-size: contain; */
        left: 4px;
    }
    .bg_gray_d:nth-child(1) span:nth-child(1){
        background:url("../assets/img/money.png") no-repeat;
        background-size: 100%;
    }
    .bg_gray_d:nth-child(2) span:nth-child(1){
        background:url("../assets/img/lifan.png") no-repeat;
        background-size: 100%;
    }
    .bg_gray_d:nth-child(3) span:nth-child(1){
        background:url("../assets/img/hongbao.png") no-repeat;
        background-size: 100%;
    }
    .personinfo:nth-child(3) .bg_gray_d:nth-child(1) span:nth-child(1){
        background:url("../assets/img/msg.png") no-repeat;
        background-size: 100%;
    }
    .personinfo:nth-child(3) .bg_gray_d:nth-child(2) span:nth-child(1){
        background:url("../assets/img/fapiao.png") no-repeat;
        background-size: 100%;
    }
    .personinfo:nth-child(3) .bg_gray_d:nth-child(3) span:nth-child(1){
        background:url("../assets/img/shoucang.png") no-repeat;
        background-size: 100%;
    }
    .personinfo:nth-child(3) .bg_gray_d:nth-child(4) span:nth-child(1){
        background:url("../assets/img/about.png") no-repeat;
        background-size: 100%;
    }
    .bg_gray_d h4{
        line-height: 26px;
        text-align: left;
        color: #333;
        padding: 8px 0 9px 47px;
        font-size: 16px;
        cursor: default;
    }
    .bg_gray_d h4 a{
        text-decoration: none;
        color: #333;
    }
    .bg_gray_d span:nth-child(3){
        display: inline-block;
        width: 7px;
        height: 13px;
        position: absolute;
        right: 15px;
        top: 14px;
        background: url('../assets/img/turenright1.png') no-repeat center;
        background-size: contain;
    }
    .footer .footerNav{
        text-align: center;
    }
    .footer .footerNav a{
        width: auto;
        font-size: 12px;
        color: #999;
        padding: 0 7px;
        border-left: 1px solid #ccc;
        text-decoration: none;
    }
    .footer .footerNav a:nth-child(1){
        border-left:1px solid transparent; 
    }
    .footer p{
        text-align: center;
        color: #999;
        font-size: 12px;
        line-height: 30px;
    }
</style>