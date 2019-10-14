<template>
  <main id="login1">
      <div class="ophonelogin">
          <ul ophoneul>
              <li>
                  <span>
                      <div class="pt-areacode-box">
                          <i>+</i><span>{{86}}</span><em></em>
                      </div>
                  </span>
                  <input type="text" placeholder="请输入手机号" class="inputLogin1" v-model="msg">
              </li>
              <li>
                  <span class="havnum">
                      验证码
                  </span>
                  <input type="text" placeholder="请输入手机验证码" class="inputLogin1" v-model="yanzheng">
                  <span v-show="ad" class="getnum" @click="getCode()">{{yan}}</span>
                  <span v-show="!ad" class="getnum">{{a}}秒后重新发送</span>
              </li>
          </ul>
          <router-link to='' class="submit"  @click.native="verify1()">登录</router-link>
          <div class="signbox">
              <router-link to='/sign' class="sign">注册</router-link>
          </div>
      </div>
      <mt-popup v-model="popupVisible" position="" class="tan">
            {{prompts}}
        </mt-popup>
  </main>
</template>

<script>
export default {
    name:'login1',
    data(){
        return{
            popupVisible:false,
            msg:"",
            a:60,
            ad:true,
            yan:"获取验证码",
            prompts:"手机号码输入不正确，请重新输入",
            yanzheng:""
        }
    },
    methods:{
        verify1(){
            // var ab = document.getElementById("ab").value;
            if(/^1[3456789]\d{9}$/.test(this.msg)&&this.yanzheng==1234){
                this.$router.push('/home')
            }else{
                this.popupVisible=true
                this.prompts = '手机号码或验证码输入不正确，请重新输入'
                this.msg=""
            }
        },
        getCode(){
            if(/^1[3456789]\d{9}$/.test(this.msg)){
                this.ad=false
                var timer = setInterval(() => {
                    this.a--;
                    if(this.a<=0){
                        clearInterval(timer)
                        this.a=60;
                        this.ad=true
                        this.yan="重新发送验证码"
                    }
                }, 1000);
            }else{
                this.popupVisible=true
                this.prompts = '请先输入正确电话号码'
            }
        }
    }
}
</script>

<style scoped>
    .ophonelogin{
        clear: both;
    }
    .ophonelogin ul{
        margin-top: 0.3rem;
    }
    .ophonelogin ul li{
        height: 3.4rem;
        border-bottom: 0.01rem solid #f3eded;
        position: relative;
    }
    .ophonelogin ul li>span{
        width: 4.3125rem;
        height: 100%;
        line-height: 3.95rem;
        position: absolute;
        top: 0;
        left: 0;
        display: inline-block;
    }
    .pt-areacode-box{
        width: 100%;
        line-height: 3.95rem;
        color: #333;
        font-size: 0.875rem;
        position: relative;
    }
    .pt-areacode-box span{
        max-width: 50px;
        height: 59px;
        line-height: 59px;
        font-size: 16px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .pt-areacode-box em{
        width: 8px;
        height: 5px;
        display: inline-block;
        background: url('../assets/img/xiala.png') no-repeat top center;
        background-size: contain;
        vertical-align: 2px;
    }
    .pt-areacode-box i{
        font-style: normal;
    }
    .inputLogin1{
        outline: 0;
        border: none;
        height: 1.5rem;
        line-height: 1.5rem;
        padding: 1.2rem 0 0.6rem 3rem;
        font-size: 0.875rem;
        width: 100%;
        -webkit-tap-highlight-color: transparent;
    }
    .havnum{
        font-size: 0.75rem;
    }
    .ophonelogin ul li .getnum{
        width: 6.3125rem;
        font-size: 0.75rem;
        color: #0185c6;
        position: absolute;
        text-align: right;
        display: block;
        height: 2.07143rem;
        line-height: 2.07143rem;
        left: 10rem;
        top: 50%;
        margin-top: -0.75rem;
    }

    .ophonelogin .submit{
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
    .ophonelogin .signbox{
        width: 100%;
        margin-top: 0.875rem;
    }
    .ophonelogin .sign{
        float: right;
        color: #999;
        font-size: 0.75rem;
        text-decoration: none;
    }

    /* 弹出框 */
    .tan{
        background-color: black;
        border-radius: 10px;
        color: white;
        font-size: 14px;
        text-align: center;
        height: 60px;
        box-sizing: border-box;
        padding: 10px;
    }
</style>