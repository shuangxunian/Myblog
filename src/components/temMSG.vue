<!-- 留言模块 -->
<template>
    <div class="tMSGbox tcommonBox">
        <header>
            <h1>
                <a href="#/DetailShare" target="_blank">
                    笔记
                </a>
            </h1>
        </header>
        <section>
            <div class="headerimg">
                <img src="static/img/timg.jpg"  alt="" >
            </div>
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
        watch: {

         },
        components: { //定义组件

        },
        created() { //生命周期函数

        }
    }
</script>

<style>
    .tMSGbox section h2{
        font-weight: bold;
        line-height: 24px;
    }
    .tMSGbox section div{
        margin:15px 0;
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
