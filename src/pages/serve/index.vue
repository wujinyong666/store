<!--做服务-->
<template>
    <div class="container">
        <div class="content">
            <div class="panel" v-for="(item, index) in serveList" :key="index" @click="nailsDetails(item)">
                <div class="img-box">
                    <img :src="item.coverUrl" alt="">
                </div>
                <div class="serve-intr">
                    <div class="inner-content">
                        <p>{{ item.name }}</p>
                        <div>
                            <span>¥</span>
                            <span>{{ item.price }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import serveList from '../../../static/js/serve'
    export default {
        data () {
            return {
                serveList: serveList
            };
        },

        methods: {
            nailsDetails (data) {
                wx.removeStorage({
                    key: 'detailsData',
                    success(res) {
                        wx.setStorage({
                            key: 'detailsData',
                            data: JSON.stringify(data),
                            success: function() {
                                wx.navigateTo({
                                    url: '/pages/details/main'
                                })
                            }
                        })
                    }
                })
            }
        },
    };
</script>

<style lang="less">
    @import '../../../static/css/common.less';
    @import "./serve";
</style>
