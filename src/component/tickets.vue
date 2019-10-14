<template>
  <main id="tickets">
      <div class="time">
          <div class="col1">
              <h2></h2>
              <p class="save-time">
                  还剩
                  <span>{{boj.hour}}</span>
                  :
                  <span>{{boj.minute}}</span>
                  :
                  <span>{{boj.second}}</span>
              </p>
              {{getDate()}}
              <router-link to='' v-for="(v,i) in list1">
                  <div class="pic">
                      <img :src="v.img" alt="">
                      <p>{{v.content}}</p>
                  </div>
                  <div class="intro">
                      <h3>{{v.title}}</h3>
                      <div class="price">
                          <em>￥</em>
                          <i>{{v.price}}</i>起
                          <router-link to=''>
                              更多抢购<b></b>
                          </router-link>
                      </div>
                  </div>
              </router-link>
          </div>
      </div>
      <ul class="ticketul">
          <li v-for="(v,i) in list">
              <router-link to=''>
                  <div class="tiLeft">
                      <h3>{{v.title}}</h3>
                      <p>{{v.content}}</p>
                  </div>
                  <img :src="v.img" alt="">
              </router-link>
          </li>
      </ul>
  </main>
</template>

<script>
export default {
    name:'tickets',
    data(){
        return{
            list:"",
            list1:"",
            boj:{

            }
        }
    },
    methods:{
        tow(n) {
            return n >= 0 && n < 10 ? '0' + n : '' + n;
        },
         getDate(){
             
            let timer = setInterval(()=> {
                let oDate = new Date();//获取现在日期对象
                let oldTime = oDate.getTime();//现在距离1970年的毫秒数
                let newDate = new Date('2029/11/1 00:00:00');//获取指定日期对象
                let newTime = newDate.getTime();//当前距离1970年的毫秒数
                // let boj=null;
                let second = Math.floor((newTime - oldTime) / 1000);//未来时间距离现在的秒数
                let hour = Math.floor(second / 3600);
                second %= 3600; 
                let  minute = Math.floor(second / 60);
                second %= 60;
                this.boj = {
                    hour:this.tow(hour),
                    minute:this.tow(minute),
                    second:this.tow(second)
                }

            },1000)
        }
    },
    mounted(){
       this.$http.get('./data/guanggao.json')
           .then( (response)=> {
                // console.log(response);
                this.list = response.data.pros,
                this.list1 = response.data.piv
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
                // always executed
            });
    },
    
}
</script>

<style scoped>
    #tickets{
        margin-top: 1rem;
        background: white;
    }
    .col1{
        padding: 0.26667rem 0.4rem 0.4rem;
        position: relative;
        border-bottom: 0.01333rem solid #e4e4e4;
        overflow: hidden;
    }
    .col1 h2{
        height: 2.5rem;
        width: 6rem;
        background-position: -20px -36px;
        /* transform: scale(0.5);  */
        zoom: 0.6;
        background: url("../assets/img/rBLkBlqo1SmAXKh2AAATQxd5x9Q718.png")
    }
    .col1 a{
        margin-top: 1rem;
    }
    .save-time{
        position: absolute;
        top: 1.2rem;
        right: 0.4rem;
        color: #666;
        font-size: 0.875rem;
    }
    .save-time span{
        display: inline-block;
        width: 28px;
        height: 28px;
        text-align: center;
        background-color: #666;
        color: white;
        border-radius: 2px;
    }
    /* 图片 */
    .pic{
        width: 36%;
        height: 100%;
        float: left;
        position: relative;
        margin-top: 0.875rem;
        /* margin-left: 1rem; */
    }
    .pic img{
        width: 100%;
        height: 100%;
    }
    .pic p{
        height: 1rem;
        line-height: 1rem;
        color: #fff;
        font-size: 0.875rem;
        background: #ff5f5f;
        padding: 0 .13333rem;
        position: absolute;
        left: 0;
        top: 0;
    }
    .intro{
        width: 60%;
        height: 5rem;
        float: right;
        position: relative;
        margin-top: 0.875rem;
    }
    .intro h3{
        max-height: 2rem;
        color: #404040;
        font-size: 0.75rem;
        line-height: 1rem;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
    .price{
        width: 100%;
        font-size: 0.75rem;
        color: #666;
        position: absolute;
        left: 0;
        bottom: 0;
    }
    .price i{
        font-style: normal;
        font-size: 0.875rem;
        color: #ff2244;
    }
    .price a{
        list-style: none;
        color: #333;
        text-decoration: none;
        margin-right: 0rem;
        position: relative;
        right: -3rem;
    }
    .price a b{
        width: 0.75rem;
        height: 0.75rem;
        background: url("../assets/img/arrowyou.png") no-repeat center center;
        background-size: contain;
        display: inline-block;
        margin-left: .13333rem;
    }


    .ticketul{
        overflow: hidden;
        padding: 10px;
        border-top: 1px solid #efe9e9;
        margin-top: 1rem;
    }
    
    .ticketul li{
        width: 50%;
        float: left;
        /* border: 1px solid #efe9e9; */
        border-right: 1px solid #efe9e9;
        box-sizing: border-box;
        padding: 0.5rem;
    }
    .ticketul li div{
        /* width: 50%; */
        float: left;
    }
    .ticketul li h3{
        line-height: 0.53333rem;
        font-size: 0.875rem;
        margin-top: 0.2rem;
        color: #333;
    }
    .ticketul li p{
        color: #ebb73f;
        /* height: 0.37333rem; */
        font-size: 0.14rem;
        padding: 0 .26667rem;
        display: inline-block;
        border: 1px solid #ebb73f;
        border-radius: 0.26667rem;
        margin-top: 0.8rem;
    }
    .ticketul li img{
        display: block;
        float: right;
        width: 30%;
    }
</style>