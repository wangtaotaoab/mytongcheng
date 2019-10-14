<template>
  <main id="login">
       <div class="loginTop">
        <ul>
            <li @click="msg='login1'" :class='{login1:true,one:msg=="login1"}'>验证码登陆</li>
            <li @click="msg='login2'" :class='{login2:true, one:msg=="login2"}'>账号密码登陆</li>
            <component :is="msg"></component>
        </ul>        

       </div>
       <div class="loginfooter">
           <span>登录即代表您已阅读并同意</span> <router-link to=''>《服务协议及隐私政策》</router-link>
           <div>
               <router-link to=''>关于同程</router-link>
               <router-link to=''>意见反馈</router-link>
               <router-link to=''>客服电话</router-link>
           </div>
           <p>©2019同程旅游</p>
       </div>
  </main>
</template>

<script>
import login1 from '../component/login1.vue'
import login2 from '../component/login2.vue'
export default {
    name:'login',
    data(){
        return{
            msg:'login1'
        }
    },
    methods:{
        change(){
            // this.msg = !this.msg;
        }
    },
    components:{
        login1,
        login2
    }
}
</script>

<style scoped>
    body{
        max-width: 640px;
        height: 100%;
        margin: 0 auto;
        min-width: 320px;
        background: #fff;
        position: relative;
    }
    #login{
        background-color: white;
    }
    .loginTop{
        width: 100%;
        height: 3rem;
        padding: 0px 30px;
        box-sizing: border-box;
        border-bottom: 1px solid #cccccc;
    }
    .login1,.login2{
        float: left;
        width: 50%;
        font-size: 0.875rem;
        text-align: center;
        line-height: 3rem;
        position: relative;
        border-bottom: 2px solid transparent;
    }
    .login1{
        box-sizing: border-box;
        padding:0px 10px; 
    }
    .login2{
        box-sizing: border-box;
        padding:0px 10px; 
    }
    .loginTop .one{
        color: #23beae;
        border-bottom: 2px solid #23beae;
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