<template>
  <main id="donghua">
      <transition  @before-enter="beforeEnter" @enter="enter" @after-enter="atfterEnter">
          <div class="ball" v-show="flag"></div>
      </transition>
      <input type="button" value="按钮" @click="flag=!flag">
      
  </main>
</template>

<script>
export default {
    name:"donghua",
    data(){
        return{
            flag:false 
        }
    },
    methods:{
        // 注意: 动画钩子函数的第一个参数el 表示要执行的动画的那个dom元素，是个原生的js dom  对象
        //相当于el是通过doucument.getElementById('')方式获取到的原生对象
        beforeEnter(el){
            //表示动画入场之前，此时动画尚未开始，可以在beforeEnter中，
            //设置元素开始动画之前起始样式
            el.style.transform = "translate(0,0)"
            //设置小球起始动画之前的起始位置
        },
        enter(el,done){
            //这句话没有实际效果，但是如果不写，出不来动画效果
            //可以认为el.offsetWidth会动画强制刷新
            el.offsetWidth
            //enter表示动画起始之后的样式，这里可以设置小球完成之后的结束状态
            el.style.transform = "translate(150px,450px)"
            el.style.transition = "all 1s ease-in"

            //这里的done，其实就是afterEnter这个函数
            //相当于done就是atfterEnter函数的引用
            done()
        },
        atfterEnter(el){
            // 动画完成之后,会调用该函数
            this.flag = !this.flag
        }

    }
}
</script>

<style scoped>
    .ball{
        width: 15px;
        height: 15px;
        border-radius: 50%;
        background-color: red;
    }
</style>