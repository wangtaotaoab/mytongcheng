<template>
  <main id="timer">
      <div class="header">
          <span class="font" @click="backgo()"></span>
          <h2>选择日期和人数</h2>
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
      <div class="mainPage">
        <div class="calWrap">
          <div class="calTab">
            <ul>
              <li v-for="(v,i) in list" @click="back(i)" :class="{active:i==num}">
                <p class="month">{{v.time}}</p>
                <p class="lowestPrice">{{v.price}}起</p>
              </li>
            </ul>
          </div>
          <div class="calendar2-panel">
              <div>
                <ul>
                    <li class="sunday">日</li>
                    <li>一</li>
                    <li>二</li>
                    <li>三</li>
                    <li>四</li>
                    <li>五</li>
                    <li class="saturday">六</li>
                </ul>
                <ul v-for="(v,i) in list1" v-if="i==num" class="dayUl">
                    <li v-for="(val,j) in v.month" @click="change1(j,val.price)" :class="{active:j==numa}">
                        <p class="data">{{val.day}}</p>
                        <p class="dataprice">{{val.symbol}}{{val.price}}</p>
                    </li>
                </ul>
              </div>
          </div>
        </div>
        <div class="travelTip">
            <span>出游人数</span>
            <router-link to='' class="priceDesc">
                预订须知
            </router-link>
        </div>
        <div class="ticketWrapper">
            <div class="ticketbox">
                <ul>
                    <li>
                        <div>成人</div>
                        <div class="itemRight">
                            <span class="minusIcon" @click="reduce()">-</span>
                            <span class="w-num">{{this.$store.state.num1}}</span>
                            <span class="plusIcon"  @click="add()">+</span>
                        </div>
                    </li>
                    <li>
                        <div>儿童</div>
                        <div class="itemRight">
                            <span class="minusIcon" @click="reduce1()">-</span>
                            <span class="w-num">{{this.$store.state.num2}}</span>
                            <span class="plusIcon" @click="add1()">+</span>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
        <div class="confirmBox">
            <div :class="{chooseDate:true,active1:1==a}" @click="chenge1(j,price)">{{allprice}}</div>
            <router-link to='/resource' :class="{butnSure:true,btnSure1:1==a}" @click="change1()">
                <p class="netxBtn">下一步</p>
                <p class="sml">选择资源</p>
            </router-link>
        </div>
      </div>
  </main>
</template>

<script>
export default {
    name:"timer",
    data(){
      return{
        show:false,
        list:'',
        list1:'',
        num:0,
        numa:1000,
        msg:"",
        a:0,
        allprice:"请选择出游日期和人数"
      }
    },
    methods:{
      backgo(){
        this.$router.go(-1)
      },
      change(){
          this.show = !this.show
      },
      back(i){
        this.num=i;
      },
      add(){
          this.$store.commit('add')
          if(this.$store.state.num1>=99){
              this.$store.state.num1=99
          }
          this.$store.state.allprice1=this.allprice=this.msg*this.$store.state.num2*0.6+this.msg*this.$store.state.num1
      },
      reduce(){
          
          if(this.$store.state.num1<=1){
              this.$store.state.num1=1
          }else if(this.$store.state.num2>=this.$store.state.num1*2){
              
          }else{
              this.$store.commit('reduce')
          }
          this.$store.state.allprice1=this.allprice=this.msg*this.$store.state.num2*0.6+this.msg*this.$store.state.num1
      },
      add1(){
          this.$store.commit('add1')
          if(this.$store.state.num2>=this.$store.state.num1*2){
              this.$store.state.num2=this.$store.state.num1*2
          }
          this.$store.state.allprice1=this.allprice=this.msg*this.$store.state.num2*0.6+this.msg*this.$store.state.num1
      },
      reduce1(){
          this.$store.commit('reduce1')
          if(this.$store.state.num2<=0){
              this.$store.state.num2=0
          }
          this.$store.state.allprice1=this.allprice=this.msg*this.$store.state.num2*0.6+this.msg*this.$store.state.num1
      },
      change1(j,price){
          this.numa=j;
          this.msg=price;
          this.$store.state.allprice1=this.allprice=price*this.$store.state.num2*0.6+price*this.$store.state.num1
          this.a=1
      }
    },
    mounted(){
        this.$http.get('./data/table.json')
           .then( (response)=> {
                console.log(response);
                this.list = response.data.month
                this.list1 = response.data.day
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
    #timer{
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
    /* 月份 */
    .calWrap .calTab {
        position: relative;
        height: 50px;
        overflow: hidden;
        background: #faf9f9;
    }
    .calWrap .calTab ul {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 999;
        height: 100%;
        padding-left: 16px;
        white-space: nowrap;
        width: 300px;
        transition-timing-function: cubic-bezier(0.1, 0.57, 0.1, 1);
        transition-duration: 0ms;
        transform: translate(0px, 0px) translateZ(0px);
    }
    .calWrap .calTab li {
        position: relative;
        display: inline-block;
        min-width: 40px;
        max-width: 60px;
        margin-right: 46px;
        overflow: hidden;
        color: #333;
        text-align: center;
    }
    .calWrap .calTab li.active{
        color: #23beae;
        position: relative;
    }
    .calWrap .calTab li.active::after{
        position: absolute;
        bottom: -2px;
        left: 50%;
        display: inline-block;
        width: 23px;
        height: 3px;
        margin-left: -15px;
        content: "";
        background: linear-gradient(90deg,#43dea0 0,#23beae 100%);
        border-radius: 3px;
    }
    .calWrap .calTab  li .month {
        padding-top: 6px;
        font-size: 16px;
    }
    .calWrap .calTab  li .lowestPrice {
        padding-bottom: 6px;
        font-size: 12px;
        line-height: 12px;
        font-size: 10px;
    }
    .calWrap .calendar2-panel{
        background: #FFF;
        font: 12px/20px Arial,'Microsoft YaHei', sans-serif, SimSun;
        font-size: 14px;
        color: #666;
        position: relative;
        -webkit-tap-highlight-color: rgba(0,0,0,0);
    }
    .calWrap .calendar2-panel>div{
        position: relative;
        padding-bottom: 2px;
    }
    .calWrap .calendar2-panel ul{
        overflow: hidden;
        /* height: 1.3rem; */
        margin: 0;
        padding: 0;
        border-spacing: 3px 0;
        border-collapse: separate;
        width: 100%;
        -webkit-tap-highlight-color: rgba(0,0,0,0);
    }
    .calendar2-panel ul li{
        float: left;
        width: 14.28%;
        border-top: none;
        vertical-align: middle;
        text-align: center;
        line-height: 19px;
        position: relative;
        padding: 13px 0;
        font-size: 13px;
        font-weight: 700;
        color: #999;
    }
    .calendar2-panel ul li.sunday{
        color: #23beae;
    }
    .calendar2-panel ul li.saturday{
        color: #23beae;
    }
    .calendar2-panel ul li .data{
        width: 100%;
        font-size: 14px;
        text-align: center;
        height: 14px;
        line-height: 14px;
        font-weight: 100;
    }
    .calendar2-panel ul li .dataprice{
        height: 10px;
        margin-top: 6px;
        font-size: 10px;
        line-height: 12px;
        color: #ff5346;
        font-weight: 100;
    }
    .calendar2-panel ul.dayUl li.active{
        color: #fff;
        background: #23beae;
        border-radius: 4px;
    }

    .travelTip {
        padding: 0 15px;
        margin-top: 10px;
        font-size: 18px;
        line-height: 44px;
        color: #41464b;
        background: #fff;
        font-weight: bold;
    }
    .travelTip .priceDesc {
        float: right;
        font-size: 12px;
        font-weight: 400;
        color: #7b7f83;
        text-decoration: none;
    }
    .ticketbox{
        padding: 10px 15px 15px;
        color: #666;
        background: #fff;
    }
    .ticketbox ul li{
        border-radius: 4px;
        display: flex;
        -webkit-box-pack: justify;
        justify-content: space-between;
        -webkit-box-align: center;
        align-items: center;
    }
    .ticketbox ul li:nth-child(1){
        margin-bottom: 15px;
    }
    .ticketbox ul li>div{
        font-size: 14px;
        font-weight: 700;
        color: #666;
        vertical-align: middle;
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

    /* 底部结算区域 */
    .confirmBox{
        position: fixed;
        bottom: 0;
        left: 0;
        z-index: 999;
        width: 100%;
        height: 60px;
        background: #fff;
        box-shadow: 0 -1px 0 0 #f3f3f4;
        display: flex;
        -webkit-box-align: center;
        align-items: center;
    }
    .confirmBox .chooseDate{
        display: flex;
        flex: 1;
        flex-direction: column;
        font-size: 14px;
        line-height: 40px;
        color: #666;
        text-indent: 15px;
        white-space: nowrap;
    }
    .confirmBox .chooseDate.active1{
        font-size: 16px;
        font-weight: 700;
        color: #ff5346;
        vertical-align: baseline;
    }
    .confirmBox .butnSure{
        text-decoration: none;
        width: 135px;
        height: 40px;
        margin-right: 16px;
        font-size: 18px;
        line-height: 40px;
        color: #fff;
        text-align: center;
        background-image: linear-gradient(-90deg,#ff5346 0,#ff7a45 100%);
        border-radius: 22px;
        opacity: 0.4;
    }
    .confirmBox .butnSure.btnSure1{
        opacity: 1;
    }
    .confirmBox .butnSure .netxBtn{
        margin: 6px 0 4px;
        font-size: 16px;
        line-height: 14px;
    }
    .confirmBox .butnSure .sml{
        font-size: 10px;
        line-height: 10px;
    }
</style>