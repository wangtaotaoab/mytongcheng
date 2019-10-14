<template>
  <main id="login2">
      <div class="ophonelogin">
          <ul ophoneul>
              <li>
                  <span>
                      <div class="pt-areacode-box">
                          <i>+</i><span>{{86}}</span><em></em>
                      </div>
                  </span>
                  <input type="text" placeholder="请输入手机号码或邮箱" class="inputLogin1" v-model="gg">
              </li>
              <li>
                  <span class="havnum">
                      密码
                  </span>
                  <input type="text" placeholder="请输入密码" class="inputLogin1" v-model="gg1">
                  <!-- <el-input :type="showPass ? 'text' : 'password'" prefix-icon="el-icon-lock" v-model="gg1"></el-input> -->
                  <span :class="{getnum:true,getopeneyes:msg1,getcloseesyes:msg2}" @click="changebg()"></span>
              </li>
          </ul>
          <router-link to='' class="submit" @click.native="verify()">登录</router-link>
          <div class="signbox">
              <router-link to='' class="forgetpassword">忘记密码?</router-link>
              <router-link to='/sign' class="sign">注册</router-link>
          </div>
          <mt-popup v-model="popupVisible" position="">
            当前用户名不正确，请重新输入
          </mt-popup>
      </div>
  </main>
</template>

<script>
export default {
    name:'login2',
    data(){
        return{
            msg1:false,
            msg2:true,
            a1:true,
            a2:false,
            aa:'',
            popupVisible:false,
            gg:"",
            gg1:"",
            showPass:false
        }
    },
    methods:{
        changebg(){
            this.msg1 = !this.msg1;
            this.msg2 = !this.msg2;
            this.a1= !this.a1;
            this.a2= !this.a2
        },
        verify(){
            alert(this.gg1)
            if(/^1[3456789]\d{9}$/.test(this.gg)){
                if((ab==15296093496)&&(ac==1234)){
                    this.aa = '/home'
                }
            }else{
                this.popupVisible=true
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
        width: 50%;
        left: 14rem;
        top: 50%;
        background:url("")
    }
    .ophonelogin ul li .getopeneyes{
        background: url('../assets/img/eyesclose.png') no-repeat;
        background-size: 12%;
    }
    .ophonelogin ul li .getcloseesyes{
        background: url('../assets/img/eyseopen.png') no-repeat;
        background-size: 12%;
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
    .ophonelogin .forgetpassword{
        float: left;
        color: #999;
        font-size: 0.75rem;
        text-decoration: none;
    }
    .ophonelogin .sign{
        float: right;
        color: #999;
        font-size: 0.75rem;
        text-decoration: none;
    }
</style>