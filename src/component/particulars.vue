<template>
  <main class="particulars">
      <!-- <div class="box">
          <input type="text" @click="setDate2()" onfocus='this.blur();' v-model="user.birthday" :placeholder="user.birthday?user.birthday:'请选择您的生日'">
      </div> -->
      <div class="header">
          <span class="font" @click="back()"></span>
          <h2>产品详情</h2>
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
          <div class="baseinfo">
              <div class="img-wrap">
                  <div class="img big-img">
                      <img src="../assets/img/qiutian.jpg" alt="">
                      <div class="tip">跟团游<span>|</span>线路编号：24626</div>
                  </div>
                  <img src="../assets/img/guanyin.jpg" alt="" class="top-img img">
                  <div class="img more-img">
                      <img src="../assets/img/gusi.jpg" alt="">
                      <div>+6</div>
                  </div>
              </div>
              <p class="linetitle">【国庆节】宁波+舟山普陀山风景区+三大寺+南海观音+紫竹林双飞4日跟团游</p>
              <p class="subtitle">飞机航班任选 专车接站 普陀山深度游 专业礼佛导游 含2晚宁波住宿 1晚普陀精品农家 天天发班</p>
              <ul class="common-tags">
                  <li class="item">无购物</li>
                  <li class="item">祈福之旅</li>
              </ul>
              <p class="price">
                  <span><em>￥</em>1725</span>
                  <small class="gny-gray">起/人</small>
              </p>
              <div class="baitiao">
                  <span class="baitiao-icon"></span>
                  <span class="baitiao-label">程程白条：</span>
                  <span class="baitiao-text">首付¥172起</span>
                  <span class="djicon"></span>
              </div>
              <div class="w-Satisfaction">
                  <div class="satisfaction">
                      <div class="satisfaction-left">
                          <div class="rate">
                              <span>96%</span>满意度
                          </div>
                          <div class="star-wrap">
                              <p class="star"><i class="iconfont icon-xing"></i></p>
                              <p class="star"><i class="iconfont icon-xing"></i></p>
                              <p class="star"><i class="iconfont icon-xing"></i></p>
                              <p class="star"><i class="iconfont icon-xing"></i></p>
                              <p class="star"><i class="iconfont icon-xing"></i></p>
                          </div>
                      </div>
                      <div class="satisfaction-right">
                          <span class="satisfaction-txt">65人评价</span>
                          <span class="djicon"></span>
                      </div>
                  </div>
              </div>
          </div>
          <div class="label-box">
              <div class="favour-group">
                  <div class="W-redPacket">
                      <div class="redPacket">
                          <div class="text">领券</div>
                          <div class="max-width">
                              <span>150元</span>
                              <span>100元</span>
                          </div>
                          <div class="offer-right">
                              <span class="djicon"></span>
                          </div>
                      </div>
                  </div>
                  <div class="W-favour">
                      <div class="favorinfo">
                          <div class="text">专享</div>
                          <div class="max-width">
                              <span class="label">点评返现</span>
                          </div>
                          <div class="offer-right">
                              <span class="djicon"></span>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
          <div class="choosedate">
              <div class="chooesCity">
                  <span class="title">广州出发</span><i class="iconfont icon-changyongtubiao-xianxingdaochu-zhuanqu-"></i>
              </div>
              <div class="price-list-wrapper">
                  <ul class="price-list">
                      <li class="price-item" v-for="(v,i) in list">
                          <div class="lowPrice">{{v.price}}</div>
                          <div class="price-box">
                              <div class="price-box-inner">
                                  <span>{{v.time1}}</span><span>{{v.time2}}</span>
                              </div>
                          </div>
                      </li>
                      <li class="ellipsis price-item">
                          <router-link to='/timer'>
                                <div class="ellipsis-inner">
                                    <p>更多</p>
                                    <p>日期</p>
                                </div>
                          </router-link>
                      </li>
                  </ul>
              </div>
          </div>
          <div class="traffic">
              <h2 class="title">交通信息</h2>
              <div class="tips">
                  <i>*</i>该产品交通动态可选，您可在选择资源页自行选择。
              </div>
          </div>
          <div class="journey">
              <div class="head">
                  4日行程
                  <span>详细行程<em class="djicon"></em></span>
              </div>
              <div class="instruciton">
                4天3晚,飞机去飞机回
              </div>
              <div class="mystatistics">
                  <ul>
                      <li v-for="(v,i) in list1">
                          <p class="count">{{v.num}}</p>
                          <p class="item">{{v.titile}}</p>
                      </li>
                  </ul>
              </div>
              <div class="journeylist">
                  <dl>
                      <dt class="title">
                          <i>D1</i>
                          <span>各地飞机宁波</span>
                      </dt>
                      <dd class="meal">
                          入住：抵达宁波后专车接送至酒店，自行入住酒店，客服会提前3小时以上用电话和短信的方式告知客人入住酒店的方式。
                【参考酒店】：宁波南苑文昌商务酒店、格林联盟（宁波火车南站顺德路店）、宁波丽嘉盛业大酒店（世纪盛业大酒店-宁波联丰店）、宁波宏远大酒店、宁波华港宾馆、开元曼居·宁波老外滩店（原宁波江花宾馆）、宁波海怡大酒店、宁波海俱大酒店、宁波海俱文华酒店、四季青藤酒店(宁波天一广场蓬莱店)
                      </dd>
                      <dd class="border-line"></dd>
                  </dl>
                  <dl>
                      <dt class="title">
                          <i>D2</i>
                          <span>普陀山</span>
                      </dt>
                      <dd class="meal">餐食：早餐</dd>
                      <dd class="meal">入住：普陀山农家客栈</dd>
                      <div class="scenic-wrap">
                          <dd class="scenic">
                              <ul>
                                  <li class="view-item">
                                      <div class="view-item-inner">
                                          <span>途经 [短姑道头] 远眺 [南天门]</span>
                                      </div>
                                  </li>
                              </ul>
                          </dd>
                      </div>
                      <dd class="border-line"></dd>
                  </dl>
                  <dl>
                      <dt class="title">
                          <i>D2</i>
                          <span>普陀山</span>
                      </dt>
                      <dd class="meal">餐食：早餐</dd>
                      <dd class="meal">入住：具体以实际抵达时间为准。
                    【参考酒店】：宁波南苑文昌商务酒店、格林联盟（宁波火车南站顺德路店）、宁波丽嘉盛业大酒店（世纪盛业大酒店-宁波联丰店）、宁波宏远大酒店、宁波华港宾馆、开元曼居·宁波老外滩店（原宁波江花宾馆）、宁波海怡大酒店、宁波海俱大酒店、宁波海俱文华酒店、四季青藤酒店(宁波天一广场蓬莱店)</dd>
                      <div class="scenic-wrap">
                          <dd class="scenic">
                              <ul>
                                  <li class="view-item">
                                      <div class="view-item-inner">
                                          <span>途经 [短姑道头] 远眺 [南天门]</span>
                                      </div>
                                  </li>
                              </ul>
                          </dd>
                      </div>
                      <dd class="border-line"></dd>
                  </dl>
                  <dl>
                      <dt class="title">
                          <i>D2</i>
                          <span>宁波飞机各地</span>
                      </dt>
                      <dd class="meal">餐食：早餐</dd>
                      <dd class="border-line"></dd>
                  </dl>
                  <div class="to-schedule-bottom">查看详细行程</div>
                  <div class="remind">
                      <span>*</span>以上行程时间安排可能会因天气、路况等原因做相应调整，敬请谅解。
                  </div>
              </div>
          </div>
          <div class="tab-content-item">
              <h2>费用须知</h2>
              <ul>
                  <li class="cot-tit">费用包含</li>
                  <li class="cot-cot">
                      <span class="cot-flag"></span>
                      <span class="cot-cots">
                          <span class="cot-title">往返交通：</span>
                          <span>往返团队经济舱机票、燃油附加费（以实际收费标准为准）、机场建设费。</span>
                      </span>
                  </li>
                  <li class="cot-line"></li>
              </ul>
              <ul></ul>
          </div>
          <div class="other">
              <h3>其他</h3>
              <ul>
                  <li>
                      <div class="item-info">
                          <i class="iconfont icon-localoffer"></i>
                      </div>
                      <div class="item-cot">
                          <p>预订须知</p>
                          <p>
                              <span>交通、</span>
                              <span>住宿、</span>
                              <span>游览、</span>
                              <span>其它</span>
                          </p>
                      </div>
                      <div class="item-arrow">
                          <span class="djicon"></span>
                      </div>
                      <div class="listline"></div>
                  </li>
                  <li>
                      <div class="item-info">
                          <i class="iconfont icon-lingdang"></i>
                      </div>
                      <div class="item-cot">
                          <p>重要提醒</p>
                          <p>
                              <span>发团地点、</span>
                              <span>组团形式、</span>
                              <span>是否拼团</span>
                          </p>
                      </div>
                      <div class="item-arrow">
                          <span class="djicon"></span>
                      </div>
                      <div class="listline"></div>
                  </li>
                  <li>
                      <div class="item-info">
                          <i class="iconfont icon-huaban"></i>
                      </div>
                      <div class="item-cot">
                          <p>退改规则</p>
                          <p>
                              <span>温馨提醒、</span>
                              <span>旅游者解除合同、</span>
                              <span>旅行社解除合同</span>
                              
                          </p>
                      </div>
                      <div class="item-arrow">
                          <span class="djicon"></span>
                      </div>
                      <div class="listline"></div>
                  </li>
                  <li>
                      <div class="item-info">
                          <i class="iconfont icon-wo"></i>
                      </div>
                      <div class="item-cot">
                          <p>特殊人群限制</p>
                          <p>
                              <span>证件限制、</span>
                              <span>年龄限制、</span>
                              <span>户籍限制性别限制、年龄限制、人数说明、户籍限制</span>
                          </p>
                      </div>
                      <div class="item-arrow">
                          <span class="djicon"></span>
                      </div>
                      <div class="listline"></div>
                  </li>
                  <li>
                      <div class="item-info">
                          <i class="iconfont icon-tishi"></i>
                      </div>
                      <div class="item-cot">
                          <p>温馨提示</p>
                          <p>
                              <span>华东出游须知</span>
                          </p>
                      </div>
                      <div class="item-arrow">
                          <span class="djicon"></span>
                      </div>
                      <div class="listline"></div>
                  </li>
              </ul>
          </div>
          <div class="foot-notes">
              <router-link to=''>
                  <h6>同程旅游</h6>
                  <span>多重服务保障 · 快速响应 · 暖心服务</span>
                  <span class="remind"></span>
              </router-link>
          </div>
          <div class="maintab">
              <ul>
                  <li class="active">交通信息</li>
                  <li>行程概括</li>
                  <li>费用须知</li>
              </ul>
          </div>
          <div class="order-action">
              <div>
                  <span>
                      <i class="iconfont icon-shoucang"></i><em>收藏</em>
                  </span>
              </div>
              <div>
                  <span>
                      <i class="iconfont icon-tel"></i><em>电话</em>
                  </span>
              </div>
              <div>
                  <span>
                      <i class="iconfont icon-zaixiankefu"></i><em>客服</em>
                  </span>
              </div>
              <router-link to='/timer' class="btn-submit">
                    <p>立即预订</p>
              </router-link>
          </div>
      </div>
  </main>
</template>

<script>
export default {
    name:'particulars',
    data(){
       return{
           date:'',
           date2:'2010-3-2',
           list:"",
           list1:"",
           list2:"",
           user:{
               birthday:''
           },
           show:false
         }
   },
   methods:{
     setDate(){
       this.$picker.show({
         type:'datePicker',
         onOk: (date) =>{
           this.date = date
         }
       });
 
     },
     setDate2(){
 
       this.$picker.show({
         type:'datePicker',
         date:this.date2,  //初始化时间
         endTime:'2020-02-11',  //截至时间
         startTime:'2010-02-11',  //开始时间
         onOk:(e)=>{
           this.date2 = e;
         },
 
       })
 
     },
     back(){
        this.$router.go(-1)
      },
      change(){
          this.show = !this.show
      }
 
   },
    mounted(){
         console.log(this.$route.params);
         this.$http.get('./data/table.json')
           .then( (response)=> {
                // console.log(response);
                this.list = response.data.date
                this.list1 = response.data.aaa
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
                // always executed
            });  
    }

    
}
$(function(){
    $(window).scroll(function(){
		var h = $(window).scrollTop();
        // console.log(h);
        if(h>=800){
            $(".maintab").show();
        }else{
            $(".maintab").hide();
        }
		if(h>=800&&h<862){
            $(".maintab ul li:nth-child(1)").addClass('active').siblings().removeClass("active");
        }else if(h>=862&&h<1723){
            $(".maintab ul li:nth-child(2)").addClass('active').siblings().removeClass("active");
        }else if(h>=1723){
            $(".maintab ul li:nth-child(3)").addClass('active').siblings().removeClass("active");
        }
    })
    $(".maintab ul li").eq(0).click(function(){
		$("html,body").animate({"scrollTop":800},500);
	})
	$(".maintab ul li").eq(1).click(function(){
		$("html,body").animate({"scrollTop":862},500);
	})
	$(".maintab ul li").eq(2).click(function(){
		$("html,body").animate({"scrollTop":1723},500);
    })
    
    $(".price-list-wrapper .price-list li").click(function(){
        $(this).addClass("active").siblings().removeClass("active");
        $(this).children(".lowPrice").addClass("active1").parent(".price-item").siblings().children(".lowPrice").removeClass("active1");
    })
})
</script>

<style scoped>
    .particulars{
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

    /* 主页部分 */

    .baseinfo{
        margin-bottom: 10px;
        background: #fff;
    }
    .baseinfo .img-wrap{
        padding: 0 2.66666667vw;
        margin-bottom: 15px;
        overflow: auto;
    }
    .baseinfo .img-wrap .img{
        position: relative;
        width: 100%;
        height: 42.66666667vw;
        overflow: hidden;
        background-position: center;
        background-size: cover;
        object-fit: cover;
    }
    .baseinfo .img-wrap .img:nth-child(1){
        width: 64vw;
        border-radius: 8px 0 0 8px;
        float: left;
    }
    .baseinfo .img-wrap .img:nth-child(1) img{
        width: 100%;
        height: 100%;
    }
    .big-img .tip{
        position: absolute;
        bottom: 0;
        box-sizing: border-box;
        width: 100%;
        padding-left: 10px;
        font-size: 14px;
        line-height: 32px;
        color: #fff;
        background-image: linear-gradient(-180deg,rgba(0,0,0,0) 0,rgba(0,0,0,.2) 98%);
    }
    .big-img .tip span{
        position: relative;
        top: -1px;
        margin: 0 5px;
    }
    .baseinfo .img-wrap .img:nth-child(2){
        width: 29.6vw;
        height: 20.8vw;
        margin-bottom: 1.06666667vw;
        margin-left: 1.06666667vw;
        border-radius: 0 8px 0 0;
        float: left;
    }
    .baseinfo .img-wrap .img:nth-child(3){
        width: 29.6vw;
        height: 20.8vw;
        margin-left: 1.06666667vw;
        float: left;
    }
    .baseinfo .img-wrap .img:nth-child(3)>img{
        width: 29.6vw;
        height: 20.8vw;
        border-radius: 0 0 8px;
    }
    .baseinfo .img-wrap .img:nth-child(3) div{
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 1;
        font-size: 18px;
        line-height: 20.8vw;
        color: #fff;
        text-align: center;
        text-shadow: 0 0 4px rgba(0,0,0,.3);
    }

    /* 标题 */
    .baseinfo .linetitle{
        margin: 0 20px 4px;
        overflow: hidden;
        font-size: 20px;
        font-weight: 500;
        line-height: 24px;
        color: #333;
        text-overflow: ellipsis;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
    }
    .baseinfo .subtitle{
        margin: 0 20px 4px;
        font-size: 14px;
        line-height: 20px;
        color: #888;
    }
    .baseinfo .common-tags{
        height: 16px;
        margin: 0 20px 17px;
        overflow: hidden;
        font-size: 0;
    }
    .baseinfo .common-tags .item{
        box-sizing: border-box;
        display: inline-block;
        height: 16px;
        padding: 0 2px;
        margin-right: 4px;
        font-size: 12px;
        line-height: 16px;
        color: #b2b2b2;
        border: 1px solid #ccc;
        border-radius: 2px;
    }
    .baseinfo .price{
        margin: 0 20px 10px;
        overflow: hidden;
        font-size: 20px;
        font-weight: 700;
        line-height: 1;
        color: #ff6257;
    }
    .baseinfo .price .gny-gray{
        font-weight: initial;
        color: #999;
        font-size: 12px;
    }
    .baseinfo .baitiao{
        margin: 0 15px 15px;
        font-size: 13px;
        line-height: 18px;
    }
    .baseinfo .baitiao .baitiao-icon{
        position: relative;
        top: -2px;
        display: inline-block;
        width: 16px;
        height: 16px;
        margin-right: 4px;
        vertical-align: middle;
        background: url('../assets/img/cheng.png') center no-repeat;
        background-size: 100%;
    }
    .baseinfo .baitiao .baitiao-label{
        color: #ff6c00;
    }
    .baitiao .baitiao-text{
        color: #b2b2b2;
    }
    .baseinfo .baitiao .djicon{
        float: right;
        display: block;
        width: 1rem;
        height: 1rem;
        color: #b2b2b2;
        background: url('../assets/img/turenright1.png') center no-repeat;
        background-size: 30%;
    }
    .baseinfo .satisfaction{
        height: 46px;
        margin: 0 10px 10px;
        line-height: 46px;
        color: #b2b2b2;
        text-align: center;
        background: #f8f8f8;
        border-radius: 8px;
    }
    .baseinfo .satisfaction .satisfaction-left{
        float: left;
        text-align: left;
    }
    .satisfaction-left .rate{
        /* margin-top: 5px; */
        margin-left: 10px;
        font-size: 13px;
        color: #999;
    }
    .satisfaction-left .rate span{
        display: inline-block;
        margin-right: 3px;
        font-size: 18px;
        font-weight: 700;
        line-height: 24px;
        color: #333;
    }
    .satisfaction-left .star-wrap{
        float: left;
        margin-left: 10px;
        font-size: 14px;
        line-height: 8px;
        color: #ff6601;
    }
    .satisfaction-left .star-wrap .star{
        position: relative;
        float: left;
        width: 12px;
        height: 12px;
        margin-right: 2px;
        font-size: 12px;
    }
    .satisfaction-left .star-wrap .star i{
        display: inline-block;
        width: 0.5rem;
        height: 0.5rem;
        font-size: 12px;
        position: absolute;
        top: -10px;
    }

    .baseinfo .satisfaction .satisfaction-right{
        float: right;
        font-size: 14px;
        line-height: 46px;
        color: #b2b2b2;
        text-align: right;
    }
    .baseinfo .satisfaction-right .djicon{
        float: right;
        margin-right: 5px;
        display: block;
        width: 1rem;
        height: 1rem;
        color: #b2b2b2;
        background: url('../assets/img/turenright1.png') center no-repeat;
        background-size: 30%;
        margin-top: 0.75rem;
    }

    .label-box{
        margin-bottom: 10px;
        background-color: #fff; 
    }
    .W-redPacket .redPacket{
        height: 2.667rem;
        margin-left: 20px;
        clear: both;
        line-height: 48px;
        position: relative;
        overflow: hidden;
        border-bottom: none;
    }
    .W-redPacket .redPacket .text,.W-favour .favorinfo .text{
        display: inline-block;
        margin-right: 10px;
        font-size: 13px;
        color: #b2b2b2;
        vertical-align: top;
    }
    .W-redPacket .redPacket .max-width,.W-favour .favorinfo .max-width{
        display: inline-block;
        max-width: 425px;
        overflow: hidden;
    }
    .redPacket .max-width span{
        margin-right: 5px;
        position: relative;
        display: inline-block;
        height: 16px;
        padding: 0 5px;
        font-size: 12px;
        line-height: 16px;
        color: #fff;
        text-align: center;
        background: #ff6257;
        border-radius: 2px;
    }
    .redPacket .max-width span::before{
        position: absolute;
        top: 5px;
        left: -3px;
        display: block;
        width: 6px;
        height: 6px;
        content: " ";
        background: #fff;
        border-radius: 3px;
    }
    .redPacket .max-width span::after{
        position: absolute;
        top: 5px;
        right: -3px;
        display: block;
        width: 6px;
        height: 6px;
        content: " ";
        background: #fff;
        border-radius: 3px;
    }
    .redPacket .offer-right{
        float: right;
        margin-right: 15px;
        font-size: 14px;
        color: #B2B2B2;
    }
    .redPacket .offer-right .djicon,.W-favour .favorinfo .offer-right .djicon{
        float: right;
        display: block;
        width: 1rem;
        height: 1rem;
        color: #b2b2b2;
        background: url('../assets/img/turenright1.png') center no-repeat;
        background-size: 30%;
        margin-top: 0.75rem;
    }
    .W-favour .favorinfo{
        height: 48px;
        margin-left: 20px;
        clear: both;
        line-height: 48px;
        position: relative;
        overflow: hidden;
        border-bottom: none;
    }

    .max-width .label{
        box-sizing: border-box;
        display: inline-block;
        height: 16px;
        padding: 0 2px;
        margin-right: 5px;
        font-size: 12px;
        line-height: 14px;
        color: #ff7802;
        text-align: center;
        vertical-align: middle;
        background: rgba(255,102,1,.1);
        border: 1px solid #ff7802;
        border-radius: 2px;
    }
    .W-favour .favorinfo .offer-right{
        float: right;
        margin-right: 15px;
        font-size: 14px;
        color: #B2B2B2;
    }

    .choosedate {
        position: relative;
        padding: 20px 0;
        margin: 10px 0;
        color: #999;
        background: #fff;
    }
    .chooesCity{
        padding: 0 20px;
        margin-bottom: 20px;
        line-height: 1;
    }
    .chooesCity .title {
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        color: #333;
    }
    .price-list-wrapper .price-list{
        padding-right: 13.63px;
        padding-left: 20px;
        overflow: hidden;
    }
    .price-list-wrapper .price-list .price-item{
        float: left;
        width: calc(25% - 12.5px);
        height: 50px;
        margin: 0 10px 10px 0;
        overflow: hidden;
        font-size: 12px;
        line-height: 20px;
        color: #b2b2b2;
        text-align: center;
        border: 1px solid #e4e4e4;
        border-radius: 4px;
    }
    .price-list-wrapper .price-list .price-item.active{
        color: white;
        background: linear-gradient(90deg,#43dea0 0,#23beae 100%);
    }
    .price-item .lowPrice{
        margin-top: 7px;
        color: #ff5346;
    }
    .price-item .lowPrice.active1{
        color: white;
    }
    .price-item a{
        text-decoration: none;
    }
    .price-box{
        height: 20px;
    }
    .ellipsis{
        color: #23beae;
        background: #fff;
    }
    .ellipsis .ellipsis-inner{
        margin-top: 10px;
        line-height: 16px;
        font-size: 12px;
    }
    .ellipsis .ellipsis-inner p{
        color: #23beae;
        background: #fff;
    }
    .price-list li:nth-child(4n) {
        margin-right: 0px;
    }  

    /* 交通信息 */
    .traffic{
        box-sizing: border-box;
        padding: 18px 15px 0;
        margin-bottom: 10px;
        background: #fff;
    } 
    .traffic .title{
        font-size: 20px;
        font-style: normal;
        font-weight: 700;
        line-height: 1;
        color: #333;
        padding-bottom: 18px;
        margin-left: 5px;
    }
    .traffic .tips{
        padding: 0 0 14px;
        margin-top: -7px;
        font-size: 12px;
        line-height: 20px;
        color: #999;
    }
    .traffic .tips i{
        margin-right: 8px;
        color: #ff6257;
    }

    /* 行程概括 */
    .journey{
        padding: 20px 0;
        margin-bottom: 10px;
        background: #fff;
    }
    .journey .head{
        height: 25px;
        padding: 0 20px;
        font-size: 20px;
        font-weight: 700;
        line-height: 25px;
        color: #333;
    }
    .journey .head span{
        position: relative;
        float: right;
        height: 20px;
        font-size: 14px;
        font-weight: 400;
        line-height: 20px;
        color: #999;
    }
    .journey .head span em{
        float: right;
        display: block;
        width: 1rem;
        height: 1rem;
        color: #b2b2b2;
        background: url('../assets/img/turenright1.png') center no-repeat;
        background-size: 30%;
    }
    .instruciton{
        margin: 5px 20px 20px;
        font-size: 13px;
        line-height: 20px;
        color: #999;
    }
    .mystatistics{
        box-sizing: border-box;
        height: 72px;
        padding: 18px 0;
        margin: 0 10px 20px;
        background: linear-gradient(-179deg,#f2f7f7 0,#edf5f4 100%);
        border-radius: 8px;
    }
    .mystatistics ul{
        display: flex;
    }
    .mystatistics ul li{
        flex: 1;
        width: 86px;
        text-align: center;
        border-right: #ddebe7 1px solid;
    }
    .mystatistics ul li .count{
        height: 16px;
        margin-bottom: 4px;
        font-size: 16px;
        line-height: 16px;
        color: #23beae;
    }
    .mystatistics ul li .item{
        height: 17px;
        font-size: 12px;
        line-height: 17px;
        color: #9eb9b5;
    }
    .journeylist dl{
        padding: 20px 0 0 20px;
    }
    .journey dl dt.title{
        display: flex;
        min-height: 20px;
        margin-bottom: 5px;
        font-size: 14px;
        font-weight: 700;
        line-height: 20px;
        color: #333;
    }
    .journey dl dt.title i{
        position: relative;
        top: 2px;
        width: 20px;
        margin-right: 10px;
        font-weight: 700;
        color: #ccc;
    }
    .journey dl dd.border-line{
        height: 1px;
        margin-top: 20px;
        margin-right: 0;
        position: relative;
        overflow: hidden;
        border-bottom: none;
    }
    .journey dl dd{
        margin: 0 20px 0 30px;
        font-size: 13px;
        line-height: 20px;
        color: #666;
    }
    .journey dl dd.meal{
        height: 20px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .journey .scenic-wrap{
        height: 64px;
        margin-top: 10px;
        margin-left: -20px;
        overflow-y: hidden;
    }
    .journey .scenic-wrap .scenic{
        height: 70px;
        margin-right: 0;
        margin-left: 0;
        overflow-x: scroll;
    }
    .journey .scenic-wrap .scenic ul{
        display: flex;
        height: 70px;
    }
    .journey .scenic-wrap .scenic ul .view-item{
        flex: 0 0 155px;
        padding-right: 5px;
        overflow: hidden;
    }
    .journey .scenic-wrap .scenic ul .view-item:nth-child(1){
        margin-left: 40px;
    }
    .scenic ul .view-item .view-item-inner{
        box-sizing: border-box;
        display: flex;
        align-items: center;
        width: 155px;
        height: 64px;
        padding: 14px 12px;
        text-align: center;
        white-space: normal;
        background: #f2f5f9;
        border-radius: 8px;
    }
    .scenic ul .view-item .view-item-inner span{
        display: -webkit-box;
        flex: 1;
        overflow: hidden;
        font-weight: 700;
        color: #6480a3;
        text-overflow: ellipsis;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
    }

    /* 查看详情按钮 */
    .journey .journeylist .to-schedule-bottom {
        height: 40px;
        margin: 30px 20px 20px;
        font-size: 16px;
        line-height: 40px;
        color: #fff;
        text-align: center;
        background-image: linear-gradient(-90deg,#23beae 0,#43dea0 100%);
        border-radius: 20px;
    }
    .journey .journeylist .remind{
        padding: 0 20px;
        font-size: 12px;
        color: #999;
    }
    .journeylist .remind span{
        margin-right: 4px;
        font-size: 14px;
        line-height: 25px;
        color: #ff6d4f;
    }

    /* 费用须知 */
    .tab-content-item{
        padding: 20px 0 15px 20px;
        margin-top: 10px;
        background: #fff;
    }
    .tab-content-item h2{
        font-size: 1.1rem;
        font-weight: 700;
        line-height: 24px;
        color: #333;
    }
    .tab-content-item ul{
        margin-top: 5px;
    }
    .tab-content-item ul .cot-tit{
        margin-top: 0.75rem;
        font-size: 0.75rem;
        color: #999;
    }
    .tab-content-item ul .cot-cot{
        margin-top: 8px;
        margin-right: 20px;
    }
    .tab-content-item ul li .cot-flag{
        position: relative;
        top: 8px;
        width: 5px;
        height: 5px;
        margin-right: 8px;
        background: #23beae;
        border-radius: 100%;
    }
    .tab-content-item ul li .cot-cots{
        width: calc(100% - 13px);
        font-size: 14px;
        line-height: 22px;
        color: #2a2a2a;
    }
    .tab-content-item ul li .cot-cots .cot-title{
        font-size: 14px;
        font-weight: 700;
        line-height: 22px;
        color: #333;
    }
    .tab-content-item ul .cot-line{
        height: 1px;
        margin-top: 15px;
        background: #f4f4f4;
    }

    /* 其他 */
    .other{
        padding: 20px 0 15px 20px;
        margin-top: 10px;
        margin-bottom: 10px;
        background: #fff;
    }
    .other h3{
        margin-bottom: 20px;
        font-size: 20px;
        font-weight: 700;
        line-height: 24px;
        color: #333;
    }
    .other ul li{
        clear: both;
    }
    .other ul li .item-info{
        float: left;
        margin: 3px 10px 0 0;
        font-size: 20px;
        color: #ccc;
    }
    .other ul li .item-cot{
        float: left;
        width: calc(100% - 60px);
    }
    .other ul li .item-cot p:nth-child(1){
        font-size: 14px;
        font-weight: 700;
        color: #333;
    }
    .other ul li .item-cot p:nth-child(2){
        overflow: hidden;
        font-size: 13px;
        line-height: 18px;
        color: #999;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .other ul li .item-arrow{
        float: right;
        margin: 12px 15px 0 0;
        font-size: 14px;
        color: #ccc;
    }
    .other ul li .item-arrow .djicon{
        /* float: right; */
        display: block;
        width: 1rem;
        height: 1rem;
        color: #b2b2b2;
        background: url('../assets/img/turenright1.png') center no-repeat;
        background-size: 30%;
    }
    .other ul li .listline{
        clear: both;
        height: 1px;
        margin: 15.5px 0px 15px 30px;
        background: #f4f4f4;
    }

    .foot-notes{
        padding: 10px 0 20px;
    }
    .foot-notes a{
        display: block;
        font-size: 0;
        color: #98a6b8;
        text-align: center;
        background: 0 0;
        text-decoration: none;
    }
    .foot-notes h6{
        font-size: 15px;
        line-height: 21px;
    }
    .foot-notes span{
        display: inline-block;
        font-size: 12px;
        line-height: 17px;
    }
    .maintab{
        position: fixed;
        top: 0;
        right: 0;
        z-index: 200;
        display: none;
        width: 100%;
        height: 40px;
        background: #fff;
        box-shadow: 0 0 2px 0 rgba(0,0,0,0.1);
    }
    .maintab ul{
        display: flex;
    }
    .maintab ul li{
        flex: 1;
        width: 25%;
        height: 40px;
        font-size: 15px;
        line-height: 40px;
        color: #666;
        text-align: center;
    }
    .maintab ul li.active{
        position: relative;
        color: #23beae;
    }
    .maintab ul li.active::before{
        position: absolute;
        bottom: 0;
        left: 50%;
        display: inline-block;
        width: 30px;
        height: 3px;
        margin-left: -15px;
        content: "";
        background: linear-gradient(90deg,#43dea0 0,#23beae 100%);
        border-radius: 3px;
    }

    /* 立即预定 */
    .order-action {
        position: fixed;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 100;
        box-sizing: border-box;
        padding-bottom: calc(60px + var(--safe-area-inset-bottom));
        height: 60px;
        font-size: 0;
        background: #fff;
        border-top: 1px solid #f2f2f2;
        display: -webkit-box;
        display: -moz-box;
        display: -webkit-flex;
        display: flex;
        -moz-transition: height .5s ease;
        -webkit-transition: height .5s ease;
        -ms-transition: height .5s ease;
        transition: height .5s ease;
        padding-bottom: 60px;
    }
    .order-action>div{
        flex: 2;
        float: left;
        height: 60px;
        margin-right: 10px;
        background-color: #fff;
    }
    .order-action>div:nth-child(1){
        margin-left: 20px;
    }
    .order-action>div span{
        display: block;
        height: 60px;
        margin-top: 0;
        font-size: 10px;
        line-height: 32px;
        color: #999;
        text-align: center;
        letter-spacing: 0;
    }
    .order-action>div span i{
        position: relative;
        top: 4px;
        display: block;
        width: 28px;
        height: 28px;
        margin: 0 auto;
        font-size: 1.05rem;
        color: #666;
        background-size: contain;
    }
    .order-action .btn-submit{
        box-sizing: border-box;
        display: flex;
        flex: 7;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 40px;
        margin: 10px 16px 10px 0;
        font-size: 16px;
        line-height: 40px;
        background: linear-gradient(90deg,#ff7c47 0,#ff5346 100%);
        border-radius: 22px;
        text-decoration: none;
        color: white;
    }
</style>