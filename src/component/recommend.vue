<template>
  <main id="recommend">
      <div class="recommend">
          <h2>
              <em></em><span>热门推荐</span>
          </h2>
          <div class="col1">
              <ul>
                  <li v-for="(v,i) in list2">
                      <router-link to=''>{{v.adress}}</router-link>
                  </li>
                  <li>
                      <router-link to=''>
                          <i></i>
                          <i></i>
                          <i></i>
                      </router-link>
                  </li>
              </ul>
          </div>
          <div class="col2">
              <ul>
                  <li v-for="(v,i) in list3">
                      <router-link to=''>
                          <p><img :src="v.img" alt=""></p>
                          <span>
                              <b>{{v.mylebel}}</b>
                              <i></i>
                          </span>
                          <p>{{v.title}}</p>
                      </router-link>
                  </li>
              </ul>
          </div>
          <div class="more">
              <router-link to="">
                  查看更多玩法
              </router-link>
          </div>
      </div>
  </main>
</template>

<script>
export default {
    name:"recommend",
    data(){
        return{
            list2:"",
            list3:""
        }
    },
    mounted(){
       this.$http.get('./data/guanggao.json')
           .then( (response)=> {
                console.log(response);
                this.list2 = response.data.piv2,
                this.list3 = response.data.piv3
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
.recommend{
    background: white;
}
.recommend h2{
    text-align: center;
    color: #fb5300;
    font-size: 0.875rem;
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
}
.recommend h2 em{
    width: 1rem;
    height: 1rem;
    display: inline-block;
    background: url("../assets/img/rBLkBlqo1SmAXKh2AAATQxd5x9Q718.png");
    vertical-align: -0.08rem;
    margin-right: 0.13333rem;
    zoom: 0.5;
    background-position: -24px -83px;
}
.col1{
    padding: 10px 10px 0px;
    border-bottom: 1px solid #e4e4e4;
}
.col1 ul{
    overflow: hidden;
}
.col1 li{
    width: 25%;
    float: left;
}
.col1 li a{
    font-size: 0.75rem;
    height: rem;
    line-height: 1.3rem;
    text-align: center;
    display: block;
    background: #dcdada;
    border-radius: 0.75rem;
    margin-right: 1rem;
    margin-bottom: 1rem;
    text-decoration: none;
    color: #333;
}
.col1 li a i{
    width: 0.3rem;
    height: 0.3rem;
    background: #979797;
    display: inline-block;
    margin-left: 0.13333rem;
    border-radius: 50%;
    vertical-align: middle;
}

.col2{
    clear:both;
    overflow: hidden;
    padding:  10px 10px 0px;
    position: relative;
}
.col2 li{
    width: 50%;
    height: 6.5625rem;
    float: left;
    display: block;
    margin-bottom: 0.5rem;
}
.col2 a{
    height: 100%;
    display: block;
    position: relative;
    margin-right: 0.26667rem;
}
.col2 a img{
    width: 100%;
    height: 100%;
    border-radius: 0.3rem;
}
.col2 a span{
    position: absolute;
    top: 0;
    left: 0;
    padding-right: 0.4rem;
}
.col2 a span b{
    height: 0.75rem;
    line-height: 0.75rem;
    font-size: 0.45rem;
    padding-left: .10667rem;
    background: #fc5446;
    color: #fff;
    display: block;
    border-top-left-radius: .10667rem;
}
.col2 a span i{
    position: absolute;
    display: inline-block;
    width: 0;
    height: 0;
    right: 0.01333rem;
    top: 0;
    border-top: 0.75rem solid #fc5446;
    border-right: .4rem solid transparent;
}
.col2 a p:nth-child(3){
    height: 0.75rem;
    line-height: 0.75rem;
    font-size: 0.75rem;
    padding: 0.75rem 0.75rem;
    position: absolute;
    bottom: 0;
    left: 0;
    color: #fff;
    overflow: hidden;
    text-overflow: ellipsis;
    -o-text-overflow: ellipsis;
    white-space: nowrap;
}

.more{
    margin-top: .26667rem;
}
.more>a{
    color: #00a0ff;
    font-size: 0.875rem;
    text-align: center;
    display: block;
    text-decoration: none;
}
</style>