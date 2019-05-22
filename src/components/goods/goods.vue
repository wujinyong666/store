<!--商品-->
<template>
    <div class="goods flex">
        <div class="category">
            <ul>
                <li class="active">
                    所有商品
                </li>
                <li>
                    面膜
                </li>
                <li>
                    润肤
                </li>
                <li>
                    补水
                </li>
            </ul>
        </div>
        <div class="goods-list">
            <ul>
                <li v-for="(item, index) in goodsList" :key="index" class="flex goods-item">
                    <img :src="item.url" alt="" class="goods-img">
                    <div class="goods-info">
                        <p class="goods-name">{{item.name}}</p>
                        <p class="goods-summary">{{item.summary}}</p>
                        <div class="goods-bottom flex">
                            <div>
                                <span class="goods-price">¥{{item.price}}</span>
                                <span class="goods-originalPrice">¥{{item.originalPrice}}</span>
                            </div>
                            <div>
                                <span class="buy-btn">+</span>
                            </div>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "goods",
        data () {
            return {
                goodsList: [
                    {
                        id: 1,
                        name: '这是商品名称',
                        summary: '商品简要描述',
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/4VcmTqzJmm57mJ8bg2dXziyszStOOJL4fUvAMWPbU3Y!/b/dL4AAAAAAAAA&bo=IAMVAgAAAAARBwQ!&rf=viewer_4',
                        price: 100,
                        originalPrice: 200
                    },
                    {
                        id: 2,
                        name: '这是商品名称',
                        summary: '商品简要描述',
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/4VcmTqzJmm57mJ8bg2dXziyszStOOJL4fUvAMWPbU3Y!/b/dL4AAAAAAAAA&bo=IAMVAgAAAAARBwQ!&rf=viewer_4',
                        price: 100,
                        originalPrice: 200
                    },
                    {
                        id: 1,
                        name: '这是商品名称',
                        summary: '商品简要描述',
                        url: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/4VcmTqzJmm57mJ8bg2dXziyszStOOJL4fUvAMWPbU3Y!/b/dL4AAAAAAAAA&bo=IAMVAgAAAAARBwQ!&rf=viewer_4',
                        price: 100,
                        originalPrice: 200
                    }
                ]
            }
        },
    }
</script>

<style lang="less">
    @import '../../../static/css/common.less';
    @import "goods";
</style>
