<!-- 关于我 -->
<template>
    <div class="tcommonBox">
        <header>
            <h1>
                <a href="#/DetailShare" target="_blank">
                    关于我
                </a>
            </h1>
        </header>
        <section>
            <p class="">
                <img :src="this.$store.state.aboutmeObj.image?this.$store.state.aboutmeObj.image:'static/img/maoto.png'" alt="" onerror="this.onerror=null;this.src= 'static/img/maoto.png'" class="aboutmeImg">
            </p>
            <p v-html="this.$store.state.aboutmeObj.brief">{{this.$store.state.aboutmeObj.brief}}</p>
            <p>
                欢迎来到我的博客！我是YuelinWang，一个穷苦大三狗，前端小萌新；
            </p>
            <p>
                莫得offer，莫得钱钱；
            </p>
            <p>
                爱好是敲代码，联盟，看书，光遇跑图
            </p>
            <p>
                擅长各种搬运 and 读写代码；
            </p>
            <p>
                <s>最擅长写代码的方式是Ctrl+c / Ctrl+v</s>
            </p>
            <p>
                博客来自于两位大佬，<a href="https://diygod.me/">DIYgod小哥哥</a>和<a href="http://www.mangoya.cn/#/">Aimee小姐姐</a>，建于2020年7月，同月更新到<a href="https://github.com/YuelinWang/Myblog">Github</a>。
            </p>
        </section>
    </div>
</template>

<script>
    export default {
        data() { //选项 / 数据
            return {

            }
        },
        methods: { //事件处理器

        },
        components: { //定义组件

        },
        created() { //生命周期函数

        }
    }
</script>

<style>
.aboutmeImg{
    max-width:100%;
    /*height:300px;*/
}
.tcommonBox p a{
    color:#01AAED!important;
}
.tcommonBox p a:hover{
    color:#48456d!important;
}
.tcommonBox p i{
    font-style: italic;
}
.tcommonBox p b{
    font-weight: bold;
}
</style>
