<!-- 赞赏模块 -->
<template>
    <div class="tRewardBox tcommonBox">
        <header>
            <h1>
                <a href="#/DetailShare" target="_blank">
                    赞赏
                </a>
            </h1>
        </header>
        <section>
            <div class="headerimg">
                <img src="static/img/timg.jpg" alt="">
            </div>
            <h1>@赞赏说明：</h1>
            <p>
                若无特殊说明，赞赏之款项用来请我喝蜜雪冰城（*/∇＼*）
            </p>
            <p>如果我给你带来过欢乐，或者对你有所帮助，欢迎赞赏支持~</p>
            <p>有任何疑问请发邮件给我~。</p>
            <hr>
            <h1>@赞赏方式：</h1>
            <el-row   :gutter="30">
                <el-col  :span="12"   class="donate-item">
                    <div class="donate-tip">
                        <img src="static/img/wechat.png">
                        <span>微信扫一扫，向我赞赏</span>
                    </div>
                </el-col>
                <el-col :span="12"  class="donate-item">
                    <div class="donate-tip">
                        <img src="static/img/alipay.png">
                        <span>支付宝扫一扫，向我赞赏</span>
                    </div>
                </el-col>
            </el-row>
        </section>
    </div>
</template>

<script>
    import {AdmireData,initDate} from '../utils/server.js'
    export default {
        data() { //选项 / 数据
            return {
                rewardData:'',//赞赏二维码
                tableData: [{//赞赏数据
                     date: '2016-05-02',
                     name: '王小虎',
                     address: '555'
                   }]
            }
        },
        methods: { //事件处理器
            showInitDate:function(date,full){//时间处理
                return initDate(date,full)
            }
        },
        components: { //定义组件

        },
        created() { //生命周期函数
            var that = this;
            AdmireData(function(msg){//获取用户赞赏数据
                // console.log(msg);
                that.tableData = msg.data;
                that.rewardData = msg.admire_code;
            })
        }
    }
</script>

<style>
.tRewardBox section{
    padding-bottom:20px;
}
.tRewardBox section h1{
    margin: 10px 0;
    font-size: 25px;
    font-weight: 700;
    /*text-align: center;*/
    line-height: 30px;
}
.tRewardBox section p{
    margin:10px 0;
    line-height:24px;
}
.tRewardBox section hr{
    background: #ccc;
    margin-bottom: 30px;
}

.tRewardBox .donate-item{
    text-align: right;
    color:#44b549;

}
.tRewardBox .donate-item:last-child{
    text-align: left;
    color:#00a0e9;
}
.tRewardBox .donate-item img{
    width:100%;
    display: block;
    height:auto;
}
.tRewardBox .donate-item div{
    display: inline-block;
    width:150px;
    padding:0 6px;
    text-align: center;
    box-sizing: border-box;
}
.tRewardBox .donate-item div span{
    display: inline-block;
    width:100%;
    margin: 10px 0;
    text-align: center;
}
.tRewardBox .el-table__body-wrapper{
    overflow: hidden;
}
.el-table--enable-row-hover .el-table__body tr:hover>td{
    background: transparent;
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
</style>
