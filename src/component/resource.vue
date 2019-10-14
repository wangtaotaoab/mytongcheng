<template>
  <main id="resource">
      <div class="header">
          <span class="font" @click="back1()"></span>
          <h2>选择资源</h2>
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
      <div class="main-page">
          <div class="top-info">
              <div class="top-title">
                  <strong>宁波+舟山普陀山风景区+三大寺+南海观音+紫竹林双飞4日跟团游</strong>
                  <h4>飞机航班任选 专车接站 普陀山深度游 专业礼佛导游 含2晚宁波住宿 1晚普陀精品农家 天天发班 </h4>
              </div>
              <div class="top-info-content">
                  <span class="content">
                      出游日期：
                      <em>2019-10-23 出发 - 2019-10-27 到达</em>
                  </span>
                  <span class="title">
                      出游人数：
                      <em>{{this.$store.state.num1}}成人{{this.$store.state.num2}}儿童</em>
                  </span>
              </div>
          </div>
          <div>
              <section class="traffic-panel">
                  <div class="step-title">
                      航班<span class="order-notice">预订须知</span>
                  </div>
                  <div class="all-resource">
                      <div>
                          <div class="date-city">
                              <div class="traffic-tag">
                                  <div class="traffic-icon">
                                      <span>去程</span>
                                  </div>
                              </div>
                              <div class="combine">
                                  <div class="traffic-info">
                                      <span>
                                          <b>广州</b>
                                          <i class="arrow-right">→</i>
                                          <b>宁波</b>
                                      </span>
                                      <span>10月23日</span>
                                  </div>
                                  <div class="company clearfix">
                                      <p>
                                          <span>南方航空CZ3777</span>
                                          <span>经济舱</span>
                                      </p>
                                  </div>
                                  <div class="djicon djicon-icon-arrow-head-right">
                                    <span class="active">更换航班</span>
                                  </div>
                              </div>
                          </div>
                          <div class="info">
                              <div>
                                  <ul class="from">
                                      <li>7:15</li>
                                      <li>广州白云国际机场</li>
                                  </ul>
                              </div>
                              <div class="stop-line">
                                  
                                  <div class="line">
                                      <i class="flightLB_16"></i>
                                  </div>
                                  <div class="stop">
                                      <span>直达</span>
                                  </div>
                                  <div class="flight-time no-stop">
                                      2时20分
                                  </div>
                              </div>
                              <div>
                                  <ul class="to">
                                      <li>9:35</li>
                                      <li>宁波栎社国际机场</li>
                                  </ul>
                              </div>
                          </div>
                          <div class="allowance-wrap">免费托运：20kg</div>
                          <div class="reticket-btn">
                              <span>退改详情</span>
                          </div>
                      </div>
                      <div class="traffic-detail"></div>
                  </div>
              </section>
              <section class="rescource-panel">
                  <div class="res-title">附加资源</div>
                  <div class="res-content">
                      <div class="res-option">
                          <div class="res-option-info">
                              <div class="res-option-title">
                                  <span>单房差</span>
                              </div>
                              <i class="iconfont icon-tishi"></i>
                              <div class="res-option-price">
                                  <span>￥<em>290</em></span>
                                  <span>/份</span>
                              </div>
                          </div>
                          <div class="btn-group-box">
                            <div class="itemRight">
                                <span class="minusIcon" @click="reduce2()">-</span>
                                <span class="w-num">{{this.$store.state.spread}}</span>
                                <span class="plusIcon"  @click="add2()">+</span>
                            </div>
                          </div>
                      </div>
                  </div>
              </section>
              <section class="insurance-panel J-Accident">
                  <div class="step-title">
                      <b>意外险</b>
                  </div>
                  <p class="warn">我们十分关心您的出行安全：建议您像大部分旅客一样选购旅游保险，以保障您的权益与出行安全。</p>
                  <div class="insurance accident-insurance">
                      <ul class="list">
                          <li>
                              <div class="hd">
                                  <div class="left">
                                      <span class="title">平安同程境内长线保险 经典型</span>
                                      <i class="iconfont icon-tishi"></i>
                                      <span class="insurance-price">￥<em>50</em>/份</span>
                                      <p class="insurance-desc">旅游意外25万| 航班延误200元 | 医疗报销2万</p>
                                  </div>
                                  <div class="price">
                                      <i class="icon-tick"></i>
                                  </div>
                              </div>
                          </li>
                      </ul>
                  </div>
                  <div class="show-btn">
                      <span>更换保险</span>
                  </div>
              </section>
              <section class="insurance-panel"></section>
          </div>
          <section class="auction-ctrlbox">
              <div class="price-count">
                  <div class="left-price">
                      <div class="price-wrap">
                          <em class="priceText">总价:</em>
                          <em class="fuhao">¥</em>
                          <em>{{this.$store.state.allprice1}}</em>
                          <em class="detail">明细</em>
                          <i></i>
                      </div>
                  </div>
                  <div class="ctrl-submit basebtn-style J-Next-Track">
                      <p class="btn-top">下一步</p>
                      <p class="btn-bottom">填写订单</p>
                  </div>
              </div>
          </section>
      </div>
  </main>
</template>

<script>
export default {
    name:"resource",
    data(){
      return{
        show:false,
        list:""
      }
    },
    methods:{
      back1(){
        this.$router.go(-1)
      },
      change(){
          this.show = !this.show
      },
      add2(){
          this.$store.commit('add2')
          if(this.$store.state.spread>=this.$store.state.num1+this.$store.state.num2){
              this.$store.state.spread=this.$store.state.num1+this.$store.state.num2
          }else{
              this.$store.state.allprice1=this.$store.state.allprice1+this.$store.state.spread*290
          }
      },
      reduce2(){
          this.$store.commit('reduce2')
          if(this.$store.state.spread<=1){
              this.$store.state.spread=1
          }else{
              this.$store.state.allprice1=this.$store.state.allprice1-this.$store.state.spread*290
          }
      }
    },
    mounted(){
        this.$http.get('./data/table.json')
           .then( (response)=> {
                console.log(response);
                this.list = response.data.resource
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
                
            });
    }
}
</script>

<style scoped>
    #resource{
        min-width: 320px;
        max-width: 640px;
        margin: 0 auto;
        overflow-x: hidden;
        background-color: #e9ecf1;
    }
    .header{
        width: 100%;
        background: #fff;
        position: relative;
        height: 2.44rem;
    }
    .header h2{
        display: inline-block;
        width: 100%;
        text-align: center;
        line-height: 2.44rem;
        font-weight: bold;
    }
    .header span{
        display: inline-block;
    }
    .header .font{
        height: 2.44rem;
        width: 2.44rem;
        position: absolute;
        top: 0rem;
        left: 0rem;
    }
    .header .font::before{
        content: '';
        display: block;
        width: 18px;
        height: 15px;
        margin: 16px 0 0 15px;
        background: url('../assets/img/return.png') no-repeat;
        background-size: contain;
    }
    .header .more{
        position: absolute;
        top: 0;
        right: 0;
        line-height: 44px;
        padding: 0 15px 0 10px;
    }
    .header .more i{
        font-size: 30px;
        color: #23beae;
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
        z-index: 2;
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

    /* 主页 */
    .main-page{
        padding-bottom: 60px;
    }
    .main-page .top-info{
        padding-bottom: 5px;
        margin-bottom: 10px;
        background-color: #fff;
    }
    .main-page .top-info .top-title{
        position: relative;
        padding: 10px 15px;
    }
    .main-page .top-info strong {
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        color: #333;
    }
    .main-page .top-info strong:first-child {
        display: block;
        margin-bottom: 5px;
    }
    .main-page .top-info .top-title h4{
        font-size: 14px;
        font-weight: 400;
        line-height: 20px;
        color: #666;
    }
    .main-page .top-info .top-info-content {
        position: relative;
        padding: 0 15px 10px;
        font-size: 14px;
        color: #999;
    }
    .main-page .top-info .top-info-content::before {
        position: absolute;
        right: 15px;
        left: 15px;
        height: 1px;
        top: 0;
        content: "";
        background-image: linear-gradient(0deg,#f3f3f4 50%,transparent 50%);
    }
    .main-page .top-info .top-info-content span {
        display: block;
        padding-top: 10px;
        font-size: 14px;
        line-height: 18px;
        color: #999;
    }
    .main-page .top-info .top-info-content span em {
        color: #2a2a2a;
    }

    /* 航班 */
    
    .main-page .traffic-panel {
        margin-bottom: 10px;
        background-color: #fff;
    }
    .main-page .traffic-panel .all-resource {
        padding: 0 15px;
    }
    .main-page .traffic-panel .step-title {
        padding: 15px 15px 0;
        font-size: 18px;
        font-weight: 700;
        line-height: 24px;
    }
    .main-page .traffic-panel .step-title .order-notice {
        float: right;
        font-size: 14px;
        font-weight: 400;
        color: #999;
    }
    .all-resource>div{
        position: relative;
        padding: 15px 0;
        font-size: 13px;
        color: #999;
        border-top: 1px solid #f4f4f4;
    }
    .all-resource>div:nth-child(1){
        border-top: 0;
    }
    .all-resource>div .date-city{
        position: relative;
        margin-bottom: 5px;
        color: #666;
    }
    .all-resource>div .date-city .combine{
        position: relative;
    }
    .date-city .combine .traffic-info>span{
        margin-right: 10px;
        color: #999;
    }
    .date-city .combine .traffic-info>span:first-child {
        font-size: 15px;
    }
    .date-city .traffic-tag .traffic-icon {
        display: inline-block;
        padding: 0 5px;
        margin-bottom: 5px;
        font-size: 12px;
        font-style: normal;
        line-height: 16px;
        color: #fff;
        text-align: center;
        background-color: #6480a3;
        border-radius: 2px;
    }
    .traffic-detail .company {
        height: 16px;
        margin-bottom: 15px;
        font-size: 12px;
        line-height: 12px;
        color: #999;
        white-space: nowrap;
    }
    .traffic-detail .company p {
        float: left;
        height: 16px;
        font-size: 0;
    }
    .clearfix::after {
        clear: both;
    }
    .djicon-icon-arrow-head-right {
        position: absolute;
        top: 50%;
        right: 0;
        margin-top: -12px;
        color: #23beae;
    }
    .djicon-icon-arrow-head-right::before{
        line-height: 17px;
    }
    .djicon-icon-arrow-head-right .active {
        float: left;
        margin-right: 3px;
    }
    .all-resource>div .info{
        display: flex;
        height: 44px;
        margin-top: 15px;
    }
    .all-resource>div .info>div{
        width: 32.5%;
        display: inline-flex;
        flex-direction: column;
    }
    .info .from li,.info .to li{
        position: relative;
        height: 13px;
        line-height: 13px;
        text-align: left;
    }
    .info .from li:nth-child(1),.info .to li:nth-child(1){
        height: 18px;
        margin-bottom: 10px;
        font-size: 18px;
        line-height: 18px;
        color: #333;
    }
    .info .to li:nth-child(1){
        position: relative;
        left: 70px;
    }
    .info .stop-line {
        position: relative;
        height: 41px;
    }
    .info .stop-line .stop{
        position: absolute;
        bottom: 0;
        left: 50%;
        margin-bottom: 0;
        margin-left: -38px;
        /* margin-bottom: 5px; */
        font-size: 12px;
        line-height: 12px;
        color: #999;
        text-align: center;
    }
    .info .stop-line .line{
        position: relative;
        height: auto;
        color: #999;
        text-align: center;
        width: 100%;
        background: initial;
    }
    .info .stop-line .line::before{
        display: inline-block;
        position: absolute;
        top: 10px;
        right: calc(50% + 16px);
        left: initial;
        width: 80%;
        height: 0;
        content: "";
        border: 0;
        border-bottom: 1px dashed #ccc;
        border-radius: 0;
    }
    .info .stop-line .line::after{
        display: inline-block;
        position: absolute;
        content: "";
        width: 80%;
        height: 0;
        border: 0;
        border-bottom: 1px dashed #ccc;
        border-radius: 0;
        right: initial;
        left: calc(50% + 16px);
        top: 12px;
        right: -5px;
    }
    .flightLB_16{
        background: url('../assets/img/flight-cc2e471b75.png') no-repeat;
        display: inline-block;
        width: 16px;
        height: 16px;
        vertical-align: -3px;
        margin-right: 5px;
        background-position: -50px 0;
    }
    .info .flight-time {
        margin-top: 5px;
        font-size: 12px;
        line-height: 12px;
        color: #999;
        text-align: center;
    }
    .info .stop-line .flight-time {
        position: absolute;
        right: 50%;
        bottom: 0;
        margin-top: 0;
        margin-right: -38px;
    }
    /* 免费托运 */
    .allowance-wrap{
        height: 12px;
        padding: 10px;
        margin-top: 13px;
        font-size: 12px;
        line-height: 12px;
        color: #999;
        background: #f8f8f8;
        border-radius: 4px;
    }
    /* 该退详情 */
    .reticket-btn {
        padding-top: 15px;
        font-size: 13px;
        color: #6480a3;
        text-align: center;
    }

    /* 附加资源 */
    .rescource-panel {
        margin-bottom: 10px;
        background: #fff;
        display: block;

    }
    .rescource-panel .res-title {
        padding: 15px 15px 0;
        font-size: 18px;
        font-weight: 700;
        line-height: 24px;
    }
    .rescource-panel .res-content {
        padding-bottom: 15px;
    }
    .rescource-panel .res-option {
        padding: 15px 15px 0;
        display: flex;
        align-items: center;
        -webkit-box-align: center;
    }
    .rescource-panel .res-option .res-option-info {
        display: flex;
        width: 0%;
        -webkit-box-flex: 1;
        flex: 1;
        align-items: center;
        -webkit-box-align: center;
    }
    .rescource-panel .res-option .res-option-info .res-option-title {
        font-size: 14px;
        color: #333;
        display: flex;
        flex-direction: column;
    }
    .rescource-panel .res-option .res-option-info i {
        margin-left: 5px;
        font-size: 18px;
        color: #ccc;
    }
    .rescource-panel .res-option .res-option-info .res-option-price {
        margin-left: 15px;
        font-size: 14px;
        color: #ff5346;
    }
    .rescource-panel .btn-group-box {
        display: inline-block;
        font-size: 0.75rem;
    }
    .itemRight .minusIcon{
        position: relative;
        display: inline-block;
        width: 22px;
        height: 22px;
        background: #fff;
        border: 1px solid #23beae;
        border-radius: 3px;
        text-align: center;
        line-height: 22PX;
    }
    .ticketbox li .itemRight .w-num {
        display:inline-block;
        width: 29px;
        height: 24px;
        font-size: 14px;
        line-height: 24px;
        color: #666;
        text-align: center;
        background: #fff;
        border: 1px solid transparent;
        -moz-appearance: none;
        -webkit-appearance: none;
    }
    .itemRight .plusIcon{
        display: inline-block;
        position: relative;
        width: 22px;
        height: 22px;
        background: #fff;
        border: 1px solid #23beae;
        border-radius: 3px;
        text-align: center;
    }

    /* 意外险 */
    .main-page .insurance-panel {
        margin-bottom: 10px;
        background-color: #fff;
        display: block;
    }
    .main-page .insurance-panel .step-title {
        padding: 15px 15px 0;
        line-height: 24px;
        color: #999;
    }
    .main-page .insurance-panel .step-title b {
        display: inline-block;
        margin-right: 10px;
        font-size: 18px;
        font-weight: 700;
        line-height: 24px;
        color: #333;
    }
    .main-page .insurance-panel .warn {
        padding: 6px 15px;
        margin-top: 10px;
        font-size: 12px;
        line-height: 18px;
        color: #9e8052;
        background: #fff8dc;
    }
    .main-page .insurance-panel .insurance {
        padding: 0 15px;
    }
    .main-page .insurance-panel .list .hd {
        position: relative;
        box-sizing: border-box;
        display: block;
    }
    .main-page .insurance-panel .list .hd .left {
        display: inline-block;
        width: 85%;
        padding: 15px 0;
        font-size: 14px;
    }
    .main-page .insurance-panel .title {
        font-size: 14px;
        line-height: 20px;
        color: #333;
    }
    .main-page .insurance-panel .list .hd .price {
        position: absolute;
        top: 0;
        right: 0;
        margin-top: 2px;
        font-size: 16px;
        color: #333;
    }
    .main-page .insurance-panel .list .hd .left i {
        margin-right: 5px;
        font-size: 15px;
        color: #ccc;
        /* vertical-align: -5px; */
    }
    .main-page .insurance-panel .list .hd .left .insurance-price {
        margin-left: 7px;
        color: #ff5346;
        white-space: nowrap;
    }
    .main-page .insurance-panel .list .hd .left .insurance-price em {
        margin: 3px;
    }
    .main-page .insurance-panel .list .hd .left .insurance-desc {
        /* margin-top: -5px; */
        font-size: 12px;
        color: #999;
    }
    .main-page .insurance-panel .list .hd .price {
        position: absolute;
        top: 0;
        right: 0;
        margin-top: 2px;
        font-size: 16px;
        color: #333;
    }
    .main-page .insurance-panel .list .hd .price .icon-tick {
        position: relative;
        display: inline-block;
        width: 14px;
        height: 14px;
        vertical-align: -17px;
        background-color: #fff;
        border: 1px solid #dcdcdc;
        border-radius: 50%;
    }
    .main-page .insurance-panel .show-btn::before {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 1px;
        content: "";
        background-image: linear-gradient(0deg,#f3f3f4 50%,transparent 50%);
    }
    .main-page .insurance-panel .show-btn {
        position: relative;
        text-align: center;
    }
    .main-page .insurance-panel .show-btn span {
        display: inline-block;
        padding: 15px 20px 15px 10px;
        line-height: 20px;
        color: #23beae;
        font-size: 14px;
    }

    /* 结算按钮 */
    .main-page .auction-ctrlbox {
        position: fixed;
        bottom: 0;
        left: 0;
        z-index: 110;
        width: 100%;
        height: 60px;
        font-size: 14px;
        background-color: #fff;
        box-shadow: 0 -1px 0 0 #f3f3f4;
    }
    .main-page .auction-ctrlbox .price-count {
        position: relative;
        display: flex;
        height: 60px;
        padding-left: 15px;
        line-height: 60px;
        white-space: nowrap;
    }
    .main-page .auction-ctrlbox .price-count>div{
        display: inline-block;
    }
    .main-page .auction-ctrlbox .price-count .left-price {
        display: flex;
        flex: 1;
        flex-direction: column;
        justify-content: center;
        line-height: 1;
        color: #ff5346;
    }
    .main-page .auction-ctrlbox .price-count .left-price .price-wrap {
        line-height: 22px;
    }
    .main-page .auction-ctrlbox .price-count span em {
        font-size: 16px;
        font-weight: 700;
    }
    .main-page .auction-ctrlbox .price-count span .priceText {
        font-size: 12px;
        font-weight: 400;
    }
    .main-page .auction-ctrlbox .price-count span .fuhao {
        margin-right: 2px;
        font-size: 12px;
        font-weight: 600;
    }
    .main-page .auction-ctrlbox .price-count span .detail {
        margin-right: 5px;
        margin-left: 8px;
        font-size: 12px;
        font-weight: 400;
        color: #999;
        vertical-align: 1px;
    }
    .main-page .auction-ctrlbox .price-count span i {
        position: relative;
        top: 2px;
        left: 4px;
        display: inline-block;
        width: 7px;
        height: 7px;
        font-size: 0;
        border-right: 1px solid #bbb;
        border-bottom: 1px solid #bbb;
        -webkit-transform: rotate(-135deg);
        transform: rotate(-135deg);
    }
    .main-page .auction-ctrlbox .ctrl-submit {
        flex: 1;
        max-width: 135px;
        height: 40px;
        margin-top: 10px;
        margin-right: 16px;
        line-height: 40px;
        color: #fff;
        text-align: center;
        background-image: linear-gradient(-90deg,#ff5346 0,#ff7a45 100%);
        border-radius: 22px;
        opacity: 1;
    }
    .main-page .auction-ctrlbox .ctrl-submit .btn-top {
        margin-top: 3px;
        font-size: 16px;
        line-height: 22px;
        text-align: center;
    }
    .main-page .auction-ctrlbox .ctrl-submit .btn-bottom {
        font-size: 10px;
        line-height: 12px;
        text-align: center;
    }
</style>