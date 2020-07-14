<!-- 文章列表 -->
<template>
    <el-row class="sharelistBox">
        <el-col :span="24" class="s-item tcommonBox">
            <header>
                <h1>
                    <a target="_blank">
                        热门文章！
                    </a>
                </h1>
            </header>
            <div class="article-content">
                <el-row>
                    <el-button type="primary" ><a href="https://mubu.com/doc/CAYihEYUS0" target="_blank" style="text-indent:15em;color:#FFF;" round="true">git教程</a></el-button>
                </el-row>
                <p style="text-indent:2em;">
                    <a href="https://mubu.com/doc/CAYihEYUS0" target="_blank" style="text-indent:15em;color:#000;">git教程</a>
                </p>
                <hr>
                <p style="text-indent:2em;">
                    <a href="https://mubu.com/doc/a9YYeiV0Y0" target="_blank" style="text-indent:15em;">h5教程</a>
                </p>
                <hr>
                <p style="text-indent:2em;">
                    <a href="https://mubu.com/doc/5c3Q2AIhuTP" target="_blank" style="text-indent:15em;">c3教程</a>
                </p>
                <hr>
                <p style="text-indent:2em;">
                    <a href="https://mubu.com/doc/xGLYYDX2g0" target="_blank" style="text-indent:15em;">JavaScript教程</a>
                </p>
                <hr>
                <p style="text-indent:2em;">
                    <a href="https://mubu.com/doc/DMAXzFmpA3" target="_blank" style="text-indent:15em;">前端学习路线的一点心得</a>
                </p>
                <hr>
            </div>
        </el-col>
        <el-col :span="24" class="s-item tcommonBox" v-for="(item,index) in articleList" :key="'article'+index">
            <span class="s-round-date">
                <span class="month" v-html="item.month +'月'"></span>
                <span class="day" v-html="item.day +'日'"></span>
            </span>
            <header>
                <h1>
                    <a :href="item.url" target="_blank">
                        {{item.title}}
                    </a>
                </h1>
                <div class="ui label">
                    <div>{{item.cate_name}}</div>
                </div>
            </header>
            <div class="article-content">
                <p style="text-indent:2em;">
                    {{item.description}}
                </p>
                <p  style="max-height:300px;overflow:hidden;text-align:center;">
                    <img :src="item.image + (index + 1) + '.jpg'" alt="" width="296px" height="256px">
                </p>
            </div>
            <div class="viewdetail">
                <a class="tcolors-bg" :href="item.url" target="_blank">
                    阅读全文>>
                </a>
            </div>
        </el-col>
    </el-row>
</template>

<script>

    export default {
        name:'Share',
        data() { //选项 / 数据
            return {
                articleList:[{
                    url:"https://mubu.com/doc/2qhaTAKnanP",
                    title:"你真的了解回调吗",
                    month: 7,
                    day: 13,
                    cate_name:"技术文章",
                    description:"整理的一篇关于回调的文章",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/UT8EkrfHDP",
                    title:"回调地狱",
                    month: 7,
                    day: 13,
                    cate_name:"技术文章",
                    description:"欢迎来到地狱~",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/wL_2wnAxTP",
                    title:"沈阳航空航天大学新生须知",
                    month: 7,
                    day: 12,
                    cate_name:"其他",
                    description:"欢迎新生！",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/UT8EkrfHDP",
                    title:"ES6详解",
                    month: 7,
                    day: 10,
                    cate_name:"技术文章",
                    description:"持续更新，真的太难了嘤嘤嘤",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/12i79Sq9hmP",
                    title:"不会吧不会吧，不会现在还有人分不清 Cookie、Session、Token、JWT吧？",
                    month: 7,
                    day: 9,
                    cate_name:"技术文章",
                    description:"哥哥们别骂我，只是标题党，为了让你们看！",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/EBZCQzHZiP",
                    title:"Vue教程",
                    month: 7,
                    day: 8,
                    cate_name:"编程语言",
                    description:"参考价值不高，全是vue官网的内容和自己做的笔记。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/2v1TQ8yLWyP",
                    title:"2020——我的面经",
                    month: 7,
                    day: 8,
                    cate_name:"面经",
                    description:"是我太菜qaq。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/1y7fGqZhs5P",
                    title:"算法路线",
                    month: 7,
                    day: 7,
                    cate_name:"算法",
                    description:"只是本菜鸡自己设计的路线，仅供小伙伴相互讨论。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/5kBpZFR5ShP",
                    title:"前端——剑指offer",
                    month: 7,
                    day: 2,
                    cate_name:"面经",
                    description:"到处扒来的面经，可能有部分过时= =。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/DMAXzFmpA3",
                    title:"前端路线",
                    month: 6,
                    day: 10,
                    cate_name:"技术文章",
                    description:"冲鸭前端！如果你有好的路线欢迎邮件我~",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/2iVFrMbSAOP",
                    title:"原型与原型链",
                    month: 6,
                    day: 3,
                    cate_name:"技术文章",
                    description:"原型与原型链，需要一定基础才能看懂。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/1IAVBN_1IiP",
                    title:"前端模块化详解",
                    month: 5,
                    day: 27,
                    cate_name:"技术文章",
                    description:"模块化理解，规范；CommonJS/AMD/CMD/ES6等。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/la6de5DHXP",
                    title:"Webpack基本使用（详解）",
                    month: 5,
                    day: 20,
                    cate_name:"技术文章",
                    description:"关于webpack一些使用心得。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/xGLYYDX2g0",
                    title:"JavaScript教程",
                    month: 5,
                    day: 7,
                    cate_name:"编程语言",
                    description:"JS教程，来自廖雪峰，菜鸟等，还有一些自己的思路。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/CAYihEYUS0",
                    title:"不会吧不会吧，不会现在还有人不会用git吧？",
                    month: 4,
                    day: 20,
                    cate_name:"技术文章",
                    description:"哥哥们别骂我，只是标题党，为了让你们看！",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                }]
            }
        },

        methods: { //事件处理器

        },
        components: { //定义组件

        },
        watch: {
           // 如果路由有变化，会再次执行该方法
           '$route':'routeChange',
           '$store.state.keywords':'routeChange'
         },
        created() { //生命周期函数
            // console.log(this.$route);
            var that = this;
            that.routeChange();
        }
    }
</script>

<style>
/*分享标题*/
.shareTitle{
    margin-bottom: 40px;
    position: relative;
    border-radius: 5px;
    background: #fff;
    padding:15px;
}
.h1-header{
    text-align: center;
}
.shareclassTwo{
    width:100%;
}
.shareclassTwo li{
    display: inline-block;
}
.shareclassTwo li a{
    display: inline-block;
    padding:3px 7px;
    margin:5px 10px;
    color:#fff;
    border-radius: 4px;
    background: #64609E;
    border: 1px solid #64609E;
    transition: transform 0.2s linear;
    -webkit-transition: transform 0.2s linear;
}
.shareclassTwo li a:hover{
    transform: translate(0,-3px);
    -webkit-transform: translate(0,-3px);
}
.shareclassTwo li a.active{
    background: #fff;
    color:#64609E;

}
/*文章列表*/
.sharelistBox{
    transition: all 0.5s ease-out;
    font-size: 15px;
}
.headerimg{
    text-align: center;
    display: table-cell;
    vertical-align: middle;
    width:1000px;
    height: 400px;
}
img{
    max-width: 100%;
    max-height: 100%;
}

    /*.sharelistBox .viewmore a:hover,.s-item .viewdetail a:hover{
        background: #48456C;
    }*/
</style>
