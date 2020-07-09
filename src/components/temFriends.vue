<!-- 友情链接模块 -->
<template>
<div class="tFriendsBox">
    <h1>好基友(✪ω✪)</h1>
    <el-row>
        <el-col :span="12" class="tf-item" v-for="(item,index) in friendslink" :key="'f'+index">
            <a :href="item.url" target="_blank">
                <img :src="item.image?item.image:'static/img/tou.jpg'"  :onerror="$store.state.errorImg">
                <h4>{{item.name}}</h4>
                <p>{{item.description}}</p>
            </a>
        </el-col>
    </el-row>
    <h1>小伙伴</h1>
    <el-row>
        <el-col :span="12" class="tf-item" v-for="(item,index) in partnerslink" :key="'f'+index">
            <a :href="item.url" target="_blank">
                <img :src="item.image?item.image:'static/img/tou.jpg'"  :onerror="$store.state.errorImg">
                <h4>{{item.name}}</h4>
                <p>{{item.description}}</p>
            </a>
        </el-col>
    </el-row>
    <h1>巨佬！！！</h1>
        <el-row>
        <el-col :span="12" class="tf-item" v-for="(item,index) in godlink" :key="'f'+index">
            <a :href="item.url" target="_blank">
                <img :src="item.image?item.image:'static/img/tou.jpg'"  :onerror="$store.state.errorImg">
                <h4>{{item.name}}</h4>
                <p>{{item.description}}</p>
            </a>
        </el-col>
    </el-row>
</div>
</template>

<script>
import {FriendUrlData} from '../utils/server.js'
export default {
    data() { //选项 / 数据
        return {
            //好基友
            friendslink: [{
                "url"           :"https://xulu.ltd/",
                "image"         :"static/img/fLink_xunlu.jpg",
                "name"          :"寻麓",
                "description"   :"第一个一起成长的小伙伴~"
            },
            {
                "url"           :"https://objtube.github.io/front-end-roadmap/#/",
                "image"         :"static/img/fLink_luke.jpg",
                "name"          :"Luke",
                "description"   :"前端能力超强的小哥哥~"
            }],
            //小伙伴
            partnerslink:[{
                "url"           :"https://lcwebsite.cn/",
                "image"         :"https://q2.qlogo.cn/headimg_dl?dst_uin=1138779174&spec=5",
                "name"          :"LC",
                "description"   :"只有不断努力才能摆脱菜鸡等级，加油！"
            },
            {
                "url"           :"https://corsun.xyz/",
                "image"         :"https://q2.qlogo.cn/headimg_dl?dst_uin=443456429&spec=5",
                "name"          :"CorsunChen",
                "description"   :"这个人懒死了，什么也没留下来"
            }],
            //大神
             godlink: [{
                "url"           :"https://overreacted.io/",
                "image"         :"https://overreacted.io/static/profile-pic-c715447ce38098828758e525a1128b87.jpg",
                "name"          :"Dan Abramov",
                "description"   :"丹神！"
            },
            {
                "url"           :"https://www.liaoxuefeng.com/",
                "image"         :"https://tva2.sinaimg.cn/crop.0.1.635.635.180/62d8efadgw1ej30downrsj20hs0hq0ws.jpg?KID=imgbed,tva&Expires=1594271859&ssig=WPmKHx2S9X",
                "name"          :"廖雪峰",
                "description"   :"SQL/Java/JS入手"
            }],
        }
    },
    methods: { //事件处理器

    },
    components: { //定义组件

    },
    created() { //生命周期函数
        var that = this;
        FriendUrlData(function(msg){
            // console.log(msg);
            that.friendslink = msg;
        })
    }
}
</script>

<style>
.tFriendsBox{
    background: #fff;
    padding:15px;
    border-radius: 5px;
    margin-bottom: 40px;
}
.tFriendsBox h1{
    padding:15px 0;
    font-size: 25px;
    font-weight: bold;
}
.tFriendsBox .tf-item{
    transition: all 0.3s ease-out;
    border-radius: 5px;
    position: relative;
}
.tFriendsBox .tf-item:hover{
    background: rgba(230,244,250,.5);
}
.tFriendsBox .tf-item a{
    display: block;
    padding:0 10px 0 90px;
    height:90px;
}
.tFriendsBox .tf-item a img{
    width:60px;
    height:60px;
    border-radius: 50%;
    position: absolute;
    top:15px;
    left:15px;
    cursor: pointer;
    object-fit: cover;
}
.tFriendsBox .tf-item a h4{
    cursor: pointer;
    white-space: nowrap;
    text-overflow: ellipsis;
    overflow: hidden;
    font-size: 20px;
    padding-top:15px;
    font-weight: bold;
}
.tFriendsBox .tf-item a p{
    margin:10px 0;
    font-size: 12px;
    line-height: 24px;
    color:#999;
    cursor: pointer;
    white-space: nowrap;
    text-overflow: ellipsis;
}
</style>
