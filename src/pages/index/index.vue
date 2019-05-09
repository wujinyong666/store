<!--首页-->
<template>
    <div class="index-page">
        <header class="flex">
            <div class="logo mr10">
                <img src="../../../static/images/logo.png" alt="">
            </div>
            <div class="store-info">
                <h2>美美哒美丽中心</h2>
                <p class="goods-info">
                    <span><span class="count">10</span>项服务</span>
                    <span class="gap">|</span>
                    <span><span class="count">50</span>件商品</span>
                    <span class="gap">|</span>
                    <span>服务<span class="count">10000+</span>人次</span>
                </p>
                <p class="location flex">
                    <img src="../../../static/images/location.png" alt="" class="mr5">
                    <span>深圳市宝安区xxx路xx花园xx号</span>
                </p>
            </div>
        </header>
        <div class="banner">
            <swiper class="swiper" indicator-dots="true" autoplay="true" interval="5000" duration="1000">
                <block v-for="(item, index) in bannerList" :index="index" :key="key">
                    <swiper-item>
                        <image :src="item.url" class="slide-image" mode="aspectFill"/>
                    </swiper-item>
                </block>
            </swiper>
        </div>
        <div class="tabs flex mb10 mt10">
            <div v-for="(item, index) in tabsList" :key="index" @click="toggleTab(index)" :class="item.active ? 'active' : ''">
                {{ item.name }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                bannerList: [
                    {
                      id: 1,
                      url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/0nNTdm4diY0WWOhWrKL*isTIeb0RaEhC8o0dgsOocVo!/b/dFIBAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                    },
                    {
                        id: 2,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/55*YxBS2JGj5eht.T3PW7VEop8OzUWxdxnrCPkmgMrA!/b/dL8AAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                    },
                    {
                        id: 3,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/Y.TIRCAikmpFfjO6QutQwafYiGJv6vq.qXpUFiDsvFY!/b/dMAAAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                    },
                ],
                tabsList: [
                    {
                        id: 1,
                        name: '服务项目',
                        active: true,
                    },
                    {
                        id: 2,
                        name: '商品列表',
                        active: false,
                    },
                    {
                        id: 3,
                        name: '优惠活动',
                        active: false,
                    },
                ],
            };
        },

        created () {

        },

        methods: {

            toggleTab (index) {
                this.tabsList.forEach(item => {
                    item.active = false;
                });
                this.tabsList[index].active = true;
            },

        }, // methods end
    };
</script>

<style lang="less">
    @import '../../../static/css/common';
    @import "index";
</style>
