<template>
  <main id="indexfooter">
      <div class="footer-top">
          <ul>
              <li>
                  <router-link to=''>
                      <img src="../assets/img/ophone1.png" alt="">
                      <p>客服电话</p>
                  </router-link>
              </li>
              <li>
                  <router-link to=''>
                      <img src="../assets/img/rBLkBlqp.png" alt="">
                      <p>下载客户端</p>
                  </router-link>
              </li>
              <li>
                  <router-link to=''>
                      <img src="../assets/img/mytongcheng.png" alt="">
                      <p>我的同程</p>
                  </router-link>
              </li>
          </ul>
      </div>
      <div class="footer-buttom">
        <router-link to=''>电脑版</router-link>
        <router-link to=''>
            <i></i>简体中文
        </router-link>
        <router-link to=''>意见反馈</router-link>
      </div>
      <div class="footerlast">©2019同程旅游</div>
  </main>
</template>

<script>
export default {

}
</script>

<style scoped>
    .footer-top ul{
        display: flex;
        width: 100%;
        align-items: center;
        justify-content: space-around;
    }
    .footer-top ul li img{
        width: 43%;
        height: 43%;
        display: block;
        margin: 0 auto;

    }
    .footer-top ul li:nth-child(2) img{
        width: 34%;
        height: 34%;
        display: block;
        margin: 0 auto;
        
    }
    .footer-top ul li p{
        color: #666;
        font-size: 0.75rem;
        margin-top: 0.333rem;
    }
    .footer-top ul li a{
        text-decoration: none;
    }

    .footer-buttom{
        text-align: center;
        padding-top: 0.6rem;
    }
    .footer-buttom a{
        display: inline-block;
        line-height: .21333rem;
        padding: 0 .26667rem 0 .4rem;
        text-decoration: none;
        font-size: 0.625rem;
        color: #999;
        position: relative;
    }
    .footer-buttom a:nth-child(2) i{
        width: 0.925rem;
        height: 0.475rem;
        margin-right: 0.3rem;
        display: inline-block;
        background: url("../assets/img/china.png") no-repeat;
    }
    .footerlast{
        background: #f0f4f5;
        color: #999;
        font-size: .32rem;
        text-align: center;
        padding: .4rem 0;
    }
</style>