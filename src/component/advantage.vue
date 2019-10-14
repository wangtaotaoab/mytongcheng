<template>
  <main id="advantage">
      <div class="advantage">
          <ul>
              <li>
                  <i></i>
                  <p>价格公正</p>
                  <span>价格公开透明，请安心购买</span>
              </li>
              <li>
                  <i></i>
                  <p>产品丰富</p>
                  <span>出行产品，全品类覆盖，一站式服务</span>
              </li>
              <li>
                  <i></i>
                  <p>品质保证</p>
                  <span>精挑细选，产品优选，放心出行</span>
              </li>
              <li>
                  <i></i>
                  <p>专业顾问</p>
                  <span>24小时专业客服，一对一服务</span>
              </li>
          </ul>
      </div>
  </main>
</template>

<script>
export default {

}
</script>

<style scoped>
    .advantage{
        margin-top: 0.625rem;
        background: white;
    }
    .advantage ul{
        padding: 1.5625rem 2.25rem 0.8rem;
    }
    .advantage ul li{
        color: #9f8a70;
        position: relative;
        padding-left: 1.5rem;
        margin-bottom: 0.5rem;
    }
    .advantage ul li i{
        width: 2rem;
        height: 2rem;
        display: inline-block;
        position: absolute;
        background-color: gold;
        left: -0.5rem;
        zoom: 0.8;
        background: url("../assets/img/rBLkBlqo1SmAXKh2AAATQxd5x9Q718.png");
       
    }
    .advantage ul li:nth-child(1) i{
        background-position: -16px -141px;
    }
    .advantage ul li:nth-child(2) i{
        background-position: -87px -141px;
    }
    .advantage ul li:nth-child(3) i{
        background-position: -158px -146px;
    }
    .advantage ul li:nth-child(4) i{
        background-position: -230px -141px;
    }
    .advantage ul li p{
        font-size: 0.875rem;
        padding-left: 1rem;
    }
    .advantage ul li span{
        font-size: 0.25rem;
        padding-left: 1rem;
    }
</style>