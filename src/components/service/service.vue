<!-- 服务 -->
<template>
    <div class="service">
        <section class="project mt10" v-for="(item, index) in serviceList" :key="index">
            <img :src="item.url" alt="">
            <div class="service-info">
                <h3>{{item.name}}</h3>
                <p class="duration flex">
                    <img src="../../../static/images/time.png" alt="">
                    <span>服务时长{{item.duration}}分钟</span>
                </p>
                <div class="price-box flex">
                    <div>
                        <span class="price mr10">¥ {{item.price}}</span>
                        <span class="original-price">¥ {{item.originalPrice}}</span>
                    </div>
                    <div>
                        <span class="appointments">预约</span>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
    export default {
        name: "service",
        data () {
            return {
                serviceList: [
                    {
                        type: 1,
                        id: 1,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/wM*dgQGgux0Wa6XxPbyu3epVIhOju*s9PgpEqyr96Dg!/b/dLgAAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                        name: '安脂特价甲油手部套餐',
                        price: 100,
                        originalPrice: 200,
                        duration: 60,
                    },
                    {
                        type: 1,
                        id: 2,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/wM*dgQGgux0Wa6XxPbyu3epVIhOju*s9PgpEqyr96Dg!/b/dLgAAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                        name: '安脂特价甲油手部套餐',
                        price: 100,
                        originalPrice: 200,
                        duration: 60,
                    },
                    {
                        type: 1,
                        id: 3,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/wM*dgQGgux0Wa6XxPbyu3epVIhOju*s9PgpEqyr96Dg!/b/dLgAAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                        name: '安脂特价甲油手部套餐',
                        price: 100,
                        originalPrice: 200,
                        duration: 60,
                    },
                    {
                        type: 1,
                        id: 4,
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/wM*dgQGgux0Wa6XxPbyu3epVIhOju*s9PgpEqyr96Dg!/b/dLgAAAAAAAAA&bo=IAMVAgAAAAARFxQ!&rf=viewer_4',
                        name: '安脂特价甲油手部套餐',
                        price: 100,
                        originalPrice: 200,
                        duration: 60,
                    }
                ],
            }
        },
    }
</script>

<style lang="less">
    @import "service";
</style>
