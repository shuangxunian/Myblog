<!-- 文章列表 -->
<template>
    <el-row class="sharelistBox">
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
                    url:"https://mubu.com/doc/xGLYYDX2g0",
                    title:"JavaScript教程",
                    data:"2020年08月02日"
                }],
                suanfa:[{
                    url:"https://mubu.com/doc/38BDb8R8imP",
                    title:"八大算法",
                    data:"2020年08月02日"
                }],
                mianjing:[{
                    url:"http://html.wangyuelin.xyz/004.html",
                    title:"端口可以用6666吗",
                    data:"2020年01月01日"
                }],
                qita:[{
                    url:"http://html.wangyuelin.xyz/005.html",
                    title:"博客v1.0归档",
                    data:"2020年08月02日"
                },{
                    url:"http://html.wangyuelin.xyz/003.html",
                    title:"731记",
                    data:"2020年07月31日"
                },{
                    url:"http://html.wangyuelin.xyz/000.html",
                    title:"沈航新生问题汇总",
                    data:"2020年07月28日"
                },{
                    url:"http://html.wangyuelin.xyz/002.html",
                    title:"717记",
                    data:"2020年07月17日"
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
