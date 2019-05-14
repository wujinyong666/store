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
                    <span><span class="count">99999+</span>人次</span>
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
        <div class="tabs flex mt10">
            <div v-for="(item, index) in tabsList" :key="index" @click="toggleTab(item)" :class="item.id === currentTab ? 'active' : ''">
                {{ item.name }}
            </div>
        </div>
        <div class="product">
            <div class="search-box">
                <input confirm-type="search" v-model="keyword" :placeholder="'搜索本店所有' + placeholderKeyList[currentTab]" @confirm="confirm($event)" >
                <img src="../../../static/images/search.png" alt="" @click="searchHandle(keyword)">
            </div>
            <div class="product-box mt10">
                <service v-if="currentTab === 1"></service>
                <goods v-if="currentTab === 2"></goods>
                <activity v-if="currentTab === 3"></activity>
            </div>
        </div>
        <car ref="carRef"/>
    </div>
</template>

<script>
    import service from '@/components/service/service'
    import goods from '@/components/goods/goods'
    import activity from '@/components/activity/activity'
    import car from '@/components/car/car'
    export default {
        components: {
            service,
            goods,
            activity,
            car
        },
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
                    },
                    {
                        id: 2,
                        name: '商品列表',
                    },
                    {
                        id: 3,
                        name: '优惠活动',
                    },
                ],
                currentTab: 1, // 当前选项卡 1-服务项目 2-商品列表 3-优惠活动
                keyword: '',
                placeholderKeyList: {
                    1: '服务',
                    2: '商品',
                    3: '优惠活动'
                },
            };
        },

        created () {

        },

        methods: {
            toggleTab (data) {
               this.currentTab = data.id;
            },

            // 搜索
            confirm (e) {
                console.log(e.target.value)
            },

            // 搜索
            searchHandle (val) {
                console.log(val);
            },

        }, // methods end
    };
</script>

<style lang="less">
    @import "index";
</style>
