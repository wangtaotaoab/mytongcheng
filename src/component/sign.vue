<template>
  <main id="sign">
      <div class="loginTop">
        <ul>
            <li class="title">
                <span class="pageback" @click="back()"></span>
                <h2>会员注册</h2>
            </li>
            <li class="liInput">
                  <span>
                      <div class="pt-areacode-box">
                          <i>+</i><span>{{86}}</span><em></em>
                      </div>
                  </span>
                  <input type="text" placeholder="请输入手机号" class="inputLogin1" id="ad">
              </li>
        </ul>
        <router-link to='' class="submit" @click.native="verify2()">获取短信验证码</router-link> 
       </div>
       <!-- <mt-popup v-model="popupVisible" position="bottom">
        请输入手机号
        </mt-popup> -->
       <div class="loginfooter">
           <span>登录即代表您已阅读并同意</span> <router-link to=''>《服务协议及隐私政策》</router-link>
           <div>
               <router-link to=''>关于同程</router-link>
               <router-link to=''>意见反馈</router-link>
               <router-link to=''>客服电话</router-link>
           </div>
           <p>©2019同程旅游</p>
       </div>
       <mt-popup v-model="popupVisible" position="">
            当前手机号输入不正确，请重新输入
        </mt-popup>
  </main>
</template>

<script>
export default {
    name:'sign',
    data(){
        return{
            popupVisible:false
        }
    },
    methods:{
        back(){
            this.$router.go(-1)
        },
        change(){
            this.show = !this.show
        },
        verify2(){
            var ab = document.getElementById("ad").value;
            if(/^1[3456789]\d{9}$/.test(ab)){
                
            }else{
                this.popupVisible=true
            }
        }
    }
}
</script>

<style scoped>
    .loginTop{
        width: 100%;
        height: 2.3rem;
        padding: 0px 30px;
        box-sizing: border-box;
        border-bottom: 1px solid #cccccc;
        position: relative;
    }
    .title{
        width: 100%;
        line-height: 2.3rem;
        text-align: center;
        /* font-size: 0.875rem; */
        font-weight: bold;
    }
    .title span{
        position: absolute;
        left: 0.8rem;
        top: 0.8rem;
        display: block;
        width: 18px;
        height: 15px;
        background: url("../assets/img/return.png") no-repeat;
        background-size: contain;
    }
    .title h2{
        font-weight: bold;
    }

    .loginTop .liInput{
        max-width: 640px;
        min-width: 320px;
        margin: 0 auto;
        background-color: #fff;
        padding-top: 1.4375rem;
        height: 3.4rem;
        border-bottom: 0.01rem solid #f3eded;
        position: relative;
    }
    .liInput span{
        max-width: 50px;
        height: 59px;
        line-height: 59px;
        font-size: 16px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .liInput em{
        width: 8px;
        height: 5px;
        display: inline-block;
        background: url('../assets/img/xiala.png') no-repeat top center;
        background-size: contain;
        vertical-align: 2px;
    }
    .liInput i{
        font-style: normal;
    }
    .inputLogin1{
        outline: 0;
        border: none;
        height: 1.5rem;
        line-height: 1.5rem;
        font-size: 0.875rem;
        width: 100%;
        -webkit-tap-highlight-color: transparent;
        position: absolute;
        top: 2.2rem;
        left: 3.5rem;
    }
    .loginTop .submit{
        text-decoration: none;
        height: 2.85714rem;
        line-height: 2.85714rem;
        text-align: center;
        color: #fff;
        font-size: 1.14286rem;
        background: #ff5346;
        display: block;
        border-radius: .13rem;
        margin-top: 1.42857rem;
    }


    .loginfooter{
        color: #b2b2b2;
        width: 100%;
        text-align: center;
        font-size: 0.625rem;
        line-height: 0.875rem;
        clear: both;
        position: absolute;
        bottom: 0px;
    }
    .loginfooter a{
        text-decoration: none;
        color: #b2b2b2;
        font-size: 0.75rem;
    }
    .loginfooter div{
        margin-top: 0.5rem;
    }
    .loginfooter div a{
        display: inline-block;
        width: 4rem;
        border-right:1px solid  #b2b2b2;
    }
    .loginfooter div a:nth-child(3){
        border-right:1px solid  transparent;
    }
    .loginfooter p{
        margin-top: 0.5rem;
    }
</style>