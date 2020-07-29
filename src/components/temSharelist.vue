<!-- 文章列表 -->
<template>
    <el-row class="sharelistBox">
        <el-col :span="24" class="s-item tcommonBox">
            <header>
                <h1>
                    热门文章！
                </h1>
                <h2>
                    <a href="https://mubu.com/doc/gvqRIFiMDP" target="_blank">首次进站请点此</a>
                </h2>
            </header>
            <div class="article-content">
                <el-row>
                    <el-button type="primary" ><a href="https://mubu.com/doc/CAYihEYUS0" target="_blank" style="text-indent:15em;color:#FFF;" round="true">git教程</a></el-button>
                    <el-button type="primary" ><a href="https://mubu.com/doc/a9YYeiV0Y0" target="_blank" style="text-indent:15em;color:#FFF;" round="true">h5教程</a></el-button>
                    <el-button type="primary" ><a href="https://mubu.com/doc/1U8CWlk1GDP" target="_blank" style="text-indent:15em;color:#FFF;" round="true">c3教程</a></el-button>
                    <el-button type="primary" ><a href="https://mubu.com/doc/xGLYYDX2g0" target="_blank" style="text-indent:15em;color:#FFF;" round="true">JS教程</a></el-button>
                    <el-button type="primary" ><a href="https://mubu.com/doc/DMAXzFmpA3" target="_blank" style="text-indent:15em;color:#FFF;" round="true">前端学习路线</a></el-button>
                </el-row>
                <hr>
            </div>
        </el-col>
        <el-col :span="24" class="s-item tcommonBox">
            <header>
                <h1>详细分类~</h1>
            </header>
            <br><br><br>
            <el-collapse accordion>
                <el-collapse-item title="技术文章">
                    <div class="item_wyl" v-for="(item,index) in jishu" :key="index">
                        <a :href="item.url">
                            &nbsp;&nbsp;&nbsp;&nbsp;{{item.title}}
                        </a>
                        <div class="data_wyl">
                            {{item.data}}
                        </div>
                        <hr>
                    </div>
                </el-collapse-item>
                <el-collapse-item title="编程语言">
                    <div class="item_wyl" v-for="(item,index) in biancheng" :key="index">
                        <a :href="item.url">
                            &nbsp;&nbsp;&nbsp;&nbsp;{{item.title}}
                        </a>
                        <div class="data_wyl">
                            {{item.data}}
                        </div>
                        <hr>
                    </div>
                </el-collapse-item>
                <el-collapse-item title="算法">
                    <div class="item_wyl" v-for="(item,index) in suanfa" :key="index">
                        <a :href="item.url">
                            &nbsp;&nbsp;&nbsp;&nbsp;{{item.title}}
                        </a>
                        <div class="data_wyl">
                            {{item.data}}
                        </div>
                        <hr>
                    </div>
                </el-collapse-item>
                <el-collapse-item title="面经">
                    <div class="item_wyl" v-for="(item,index) in mianjing" :key="index">
                        <a :href="item.url">
                            &nbsp;&nbsp;&nbsp;&nbsp;{{item.title}}
                        </a>
                        <div class="data_wyl">
                            {{item.data}}
                        </div>
                        <hr>
                    </div>
                </el-collapse-item>
                <el-collapse-item title="其它">
                    <div class="item_wyl" v-for="(item,index) in qita" :key="index">
                        <a :href="item.url">
                            &nbsp;&nbsp;&nbsp;&nbsp;{{item.title}}
                        </a>
                        <div class="data_wyl">
                            {{item.data}}
                        </div>
                        <hr>
                    </div>
                </el-collapse-item>
            </el-collapse>
        </el-col>
    </el-row>
</template>

<script>

    export default {
        name:'Share',
        data() { //选项 / 数据
            return {
                //https://mubu.com/doc/38BDb8R8imP
                //https://mubu.com/doc/6TBHXdZKfSP
                jishu:[{
                    url:"http://html.wangyuelin.xyz/001.html",
                    title:"端口可以用6666吗",
                    data:"2020年07月28日"
                }],
                biancheng:[{
                    url:"http://html.wangyuelin.xyz/001.html",
                    title:"端口可以用6666吗",
                    data:"2020年01月01日"
                }],
                suanfa:[{
                    url:"http://html.wangyuelin.xyz/001.html",
                    title:"端口可以用6666吗",
                    data:"2020年01月01日"
                }],
                mianjing:[{
                    url:"http://html.wangyuelin.xyz/001.html",
                    title:"端口可以用6666吗",
                    data:"2020年01月01日"
                }],
                qita:[{
                    url:"http://html.wangyuelin.xyz/000.html",
                    title:"沈航新生问题汇总",
                    data:"2020年07月28日"
                }],
                articleList:[{
                    url:"https://mubu.com/doc/6TBHXdZKfSP",
                    title:"端口可以用6666吗",
                    month: 7,
                    day: 24,
                    cate_name:"技术文章",
                    description:"关于端口的一个小问题",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/38BDb8R8imP",
                    title:"八大算法",
                    month: 7,
                    day: 24,
                    cate_name:"技术文章",
                    description:"过一遍常见算法",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/xGLYYDX2g0",
                    title:"JavaScript教程",
                    month: 7,
                    day: 24,
                    cate_name:"编程语言",
                    description:"JS教程，来自廖雪峰，菜鸟等，还有一些自己的想法，这篇文章会长时间更新。",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/M2HkG2WIOP",
                    title:"vue权限路由实现方式总结",
                    month: 7,
                    day: 24,
                    cate_name:"技术文章",
                    description:"关于vue中权限是如何实现的",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/3RMtM8rDtIP",
                    title:"js相等运算符与严格相等运算符",
                    month: 7,
                    day: 23,
                    cate_name:"技术文章",
                    description:"JS ==和===的区别",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/87cdLIYQmP",
                    title:"JavaScript：彻底理解同步、异步和事件循环(Event Loop)",
                    month: 7,
                    day: 20,
                    cate_name:"技术文章",
                    description:"彻底理解同步、异步和事件循环",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/7OmXe0cL6WP",
                    title:"Vue项目中优雅使用icon",
                    month: 7,
                    day: 20,
                    cate_name:"技术文章",
                    description:"关于icon的使用",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/6eLdvKlqZGP",
                    title:"正则表达式",
                    month: 7,
                    day: 19,
                    cate_name:"技术文章",
                    description:"关于验证各种输入是否合法等",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
                    url:"https://mubu.com/doc/LSH4mOGfwP",
                    title:"html5语义化标签",
                    month: 7,
                    day: 18,
                    cate_name:"技术文章",
                    description:"整理的一篇关于关于h5的文章，建议弄清楚html再来看",
                    image:"https://13miki.cdn.bcebos.com/menhera%2F",
                },{
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
                    url:"https://mubu.com/doc/2hp7ULPB8GP",
                    title:"前端模块化",
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
.data_wyl{
    height: 20px;
    width: 100px;
    float: right;
    font-family: "宋体", "仿宋", sans-serif;
    font-size: 13px;
    font-weight: lighter;
    color: rgba(154,154,154);
}
.item_wyl{
    height: auto;
    width: 100%;
    font-size: 20px;
}
    /*.sharelistBox .viewmore a:hover,.s-item .viewdetail a:hover{
        background: #48456C;
    }*/
</style>
