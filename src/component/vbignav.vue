<template>
  <main id="vbignav">
      <div class="bigNav">
        <ul>
            <li>
                <router-link to=''>
                    <img src="../assets/img/tongcheng01.png" alt="">
                    <p>火车票</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/jipiao.png" alt="">
                    <p>机票</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/jiudian.png" alt="">
                    <p>酒店住宿</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/jingdian.png" alt="">
                    <p>景点门票</p>
                </router-link>
            </li>
        </ul>
    </div>
    <div class="litlenav">
        <ul>
            <li>
                <router-link to='/donghua'>
                    <img src="../assets/img/chuanpiao.png" alt="">
                    <p>汽车票·船票</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/free.png" alt="">
                    <p>周边自由行</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/gentuan.png" alt="">
                    <p>周边跟团游</p>
                </router-link>
            </li>
            <li>
                <router-link to='/jingnei'>
                    <img src="../assets/img/jingneiyou.png" alt="">
                    <p>境内游</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/xiaochuan.png" alt="">
                    <p>邮轮</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/xiaoshu.png" alt="">
                    <p>出境游</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/ren.png" alt="">
                    <p>海外玩乐</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/qianzheng.png" alt="">
                    <p>签证</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/wifi.png" alt="">
                    <p>全球WiFi</p>
                </router-link>
            </li>
            <li>
                <router-link to=''>
                    <img src="../assets/img/quanbu.png" alt="">
                    <p>全部服务</p>
                </router-link>
            </li>
        </ul>
    </div>
  </main>
  
</template>

<script>
export default {
    name:'vbignav'
}
</script>

<style scoped>
    #vbignav{
        background: white;
        padding-bottom: 1rem;
    }
    .bigNav{
        margin: 0px 10px;
        border-bottom: 1px solid #eae8e8;
        overflow: hidden;
    }
    .bigNav ul li{
        float: left;
        width: 25%;
        box-sizing: border-box;
        padding: 5.5% 0%;
    }
    .bigNav ul li img{
        width: 60%;
        display: block;
        margin: 0 auto;
    }
    .bigNav ul li p{
        margin-top: 0.6rem;
        font-size: 0.775rem;
        text-align: center;
    }
    .bigNav a{
        text-decoration: none;
        color: #333;
    }
    .litlenav{
        /* margin-top: 1rem; */
        overflow: hidden;
        margin: 0px 10px;
    }
    .litlenav ul li{
        float: left;
        width: 20%;
        box-sizing: border-box;
        margin: 0%;
    }
    .litlenav ul li img{
        display: block;
        margin: 22% auto 0%;
        width: 50%;
    }
    .litlenav ul li p{
        margin-top: 0.2rem;
        font-size: 0.575rem;
        text-align: center;
    }
    .litlenav a{
        text-decoration: none;
        color: #333;
    }
</style>