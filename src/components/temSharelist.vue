<!-- 文章列表 -->
<template>
    <el-row class="sharelistBox">
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
                    <img :src="item.image" alt="" width="296px" height="256px">
                </p>
            </div>
            <div class="viewdetail">
                <a class="tcolors-bg" :href="item.url" target="_blank">
                    阅读全文>>
                </a>
            </div>
        </el-col>
        <el-col class="viewmore">
            <a v-show="hasMore" class="tcolors-bg" href="javascript:void(0);" @click="addMoreFun">点击加载更多</a>
            <a v-show="!hasMore" class="tcolors-bg" href="javascript:void(0);">暂无更多数据</a>
        </el-col>
    </el-row>
</template>

<script>

    export default {
        name:'Share',
        data() { //选项 / 数据
            return {
                articleList:[{
                    url:"https://mubu.com/doc/EBZCQzHZiP",
                    title:"Vue教程",
                    month: 7,
                    day: 8,
                    cate_name:"编程语言",
                    description:"参考价值不高，全是vue官网的内容和自己做的笔记。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/2v1TQ8yLWyP",
                    title:"2020——我的面经",
                    month: 7,
                    day: 8,
                    cate_name:"面经",
                    description:"是我太菜qaq。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/1y7fGqZhs5P",
                    title:"算法路线",
                    month: 7,
                    day: 7,
                    cate_name:"算法",
                    description:"只是本菜鸡自己设计的路线，仅供小伙伴相互讨论。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/5kBpZFR5ShP",
                    title:"前端——剑指offer",
                    month: 7,
                    day: 2,
                    cate_name:"面经",
                    description:"到处扒来的面经，可能有部分过时= =。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/2iVFrMbSAOP",
                    title:"原型与原型链",
                    month: 6,
                    day: 3,
                    cate_name:"技术文章",
                    description:"原型与原型链，需要一定基础才能看懂。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/1IAVBN_1IiP",
                    title:"前端模块化详解",
                    month: 5,
                    day: 27,
                    cate_name:"技术文章",
                    description:"模块化理解，规范；CommonJS/AMD/CMD/ES6等。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/la6de5DHXP",
                    title:"Webpack基本使用（详解）",
                    month: 5,
                    day: 20,
                    cate_name:"技术文章",
                    description:"关于webpack一些使用心得。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                },{
                    url:"https://mubu.com/doc/xGLYYDX2g0",
                    title:"JavaScript教程",
                    month: 5,
                    day: 7,
                    cate_name:"编程语言",
                    description:"JS教程，来自廖雪峰，菜鸟等，还有一些自己的思路。",
                    image:"https://acg.yanwz.cn/menhera/api.php",
                }]
            }
        },

        methods: { //事件处理器
            /*showInitDate: function(oldDate,full){
                // console.log(oldDate,full);
                return initDate(oldDate,full)
            },
            showSearchShowList:function(initpage){//展示数据
                var that = this;
                that.classId = (that.$route.query.classId==undefined?0:parseInt(that.$route.query.classId));//获取传参的classId
                that.keywords = that.$store.state.keywords;//获取传参的keywords
                that.classtwoId = that.$route.query.classtwoId==undefined?'':parseInt(that.$route.query.classtwoId);//获取传参的classtwoId
                that.sendId = that.classtwoId?that.classtwoId:that.classId;
                that.level = that.keywords ? 0 : that.classtwoId?0:1;
                // console.log(that.classId);
                ArtClassData(function(msg){
                    // console.log(msg);
                    that.shareClass = msg;
                })
                //判断当前显示的分类名称 以及子分类
                for(var i=0;i<that.shareClass.length;i++){
                    if(that.classId==that.shareClass[i].class_id){
                        that.className = that.shareClass[i].cate_name;
                        if(that.shareClass[i].ChildsSon&&that.shareClass[i].ChildsSon.length>0){
                            that.sonclassList = that.shareClass[i].ChildsSon;
                        }else{
                            that.sonclassList = '';
                        }
                    }
                }
                //初始化 文章id为0开始
                that.artId = initpage ? 0 : that.artId;
                ShowArticleAll(that.artId,that.sendId,that.keywords,that.level,(result)=>{
                    // console.log(result);
                    if(result.code==1001){
                        var msg = result.data;
                        if(msg.length>0&&msg.length<10){
                            that.hasMore = false
                        }else{
                            that.hasMore = true;
                        }
                        that.articleList = initpage ? msg : that.articleList.concat(msg);
                        that.artId = msg[msg.length-1].id;
                        // console.log(that.artId);
                    }else{
                        that.hasMore = false;
                        that.articleList = initpage ? [] : that.articleList;
                    }
                })
            },
            addMoreFun:function(){//查看更多
                this.showSearchShowList(false);
            },
            routeChange:function(){
                var that = this;
                this.showSearchShowList(true);
            }*/
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
