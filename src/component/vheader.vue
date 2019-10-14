<template>
    <main id="vheader">
        <div class="inndexTop">
            <div class="topLeft">
                广州
            </div>
            <div class="search">
                <h3>
                    <span>目的地/酒店/景点/关键字</span>
                </h3>
            </div>
            <router-link to='/my'>
                <div class="topLogin"></div>
            </router-link>
            
        </div>
    </main>
</template>

<script>
export default {
    name:"vheader",
    
}

</script>

<style scoped>
    .inndexTop{
        padding: 8px 10px;
        background-color: #fff;
        border-bottom:1px solid #eeeeee; 
        overflow: hidden;
        position: relative;
        font-weight: 400;
        /* position: fixed; */
    }

    .topLeft{
        float: left;
        font-size: 0.875rem;
        line-height: 1rem;
        color: #23beae;
        padding: 0 6% 0 0;
        position: relative;
        margin-right: 0.17rem;
        padding-top: 10px;
    }
    .topLeft::after{
        content: "";
        width: 0.5rem;
        height: 0.5rem;
        position: absolute;
        top: 0.875rem;
        right: 10%;
        background: url("../assets/img/tongindex.png")  no-repeat left top;
        content: " ";
        background-size: contain;
    }
    .search{
        width: 70%;
        border-radius: 0.875rem;
        background: #eaedf1;
        height: 1.875rem;
        margin: auto;
    }
    .search h3{
        text-align: center;
        padding: 0 .25333rem;
        line-height: 1.805rem;
        color: #93989f;
        font-size: 0.5rem;
        border-color: transparent;
    }
    .search h3::before{
        width: 0.875rem;
        height: 0.875rem;
        background: url("../assets/img/search.png") no-repeat left top;
        content: " ";
        display: inline-block;
        background-size: contain;
        vertical-align: middle;
    }
    .search h3 span{
        font-size: 0.373333rem;
        margin-left: 1rem;
    }
    .topLogin{
        width: 1rem;
        height: 1rem;
        background: url("../assets/img/tongmy.png") no-repeat left top;
        background-size: contain;
        position: absolute;
        /* right: 1.8rem; */
        right: 1rem;
        top: 0.875rem;
    }
</style>