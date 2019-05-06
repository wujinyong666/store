<template>
    <div class="details">
        <swiper v-if="bannerList.length > 0" indidator-dots="bannerList.length > 1" :autoplay="autoplay" :interval="interval">
            <block v-for="(item, index) in bannerList" :key="index">
                <swiper-item>
                    <image :src="item" mode="scaleToFill"></image>
                </swiper-item>
            </block>
        </swiper>

        <div class="plate">
            <h2>{{ detailsData.name }}</h2>
        </div>

        <div class="plate">
            <h3>服务部位</h3>
            <span class="part">{{ detailsData.part }}</span>
        </div>

        <div class="plate">
            <h3>服务时长</h3>
            <span class="serveDuration">约{{ detailsData.serveDuration }}分钟</span>
        </div>

        <div class="plate introduce">
            <h3>服务介绍</h3>
        </div>

        <section class="introduce-box">
            <div class="can-do">
                <img :src="canDoImg" alt="">
            </div>
            <div class="cover-img">
                <img :src="detailsData.coverUrl" alt="">
            </div>
            <div class="serve-details">
                <h2>服务详情</h2>
                <p v-for="(item, index) in detailsData.feature" :key="index">
                    <i></i>
                    <span>{{ item }}</span>
                </p>
            </div>
        </section>

        <section class="price-box">
            <div class="price">
                <span>¥</span>
                <span>{{ detailsData.price }}</span>
            </div>
            <div class="phone" @click="makePhone">
                <div class="phone-img">
                    <img src="../../../static/tabs/phone.png" alt="">
                </div>
            </div>
            <!--<div class="download" @click="downloadHandle">
                <div class="download-img">
                    <img src="../../../static/tabs/download.png" alt="">
                </div>
            </div>-->
        </section>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                detailsData: {},
                bannerList: [],
                autoplay: true,
                interval: 3000,
                canDoImg: 'http://m.qpic.cn/psb?/V14IXSk615MNiG/fAclxzFIZx0oi7QeeKe8Dnbfb4bcKOxHVNH76u90Bmk!/b/dLkAAAAAAAAA&bo=8gKjAQAAAAARB2I!&rf=viewer_4',
            };
        },

        onShow () {
            this.bannerList = [];
            wx.showLoading({title: '加载中', icon: 'loading', duration: 10000});
            let that = this;
            wx.getStorage({
                key:'detailsData',
                success:function(res){
                    that.detailsData = JSON.parse(res.data);
                    that.bannerList = that.detailsData.bannerList;
                    wx.hideLoading()
                }
            })
        },

        onHide () {
            console.log("123456")
        },

        destroyed () {
            console.log("333")
        },

        created () {

        },

        methods: {
            makePhone () {
                wx.makePhoneCall({
                    phoneNumber: '10000'
                })
            },

            downloadHandle () {
                let that = this;
                wx.downloadFile({
                    url: that.detailsData.coverUrl,
                    success:function(res){
                        let path = res.tempFilePath;
                        wx.saveImageToPhotosAlbum({
                            filePath: path,
                            success(res) {
                                console.log(res)
                            },
                            fail(res) {
                                console.log(res)
                            },
                            complete(res) {
                                console.log(res)
                            }
                        })
                    },fail:function(res){
                        wx.showToast({
                            title: '网络错误',
                            icon: 'loading',
                            duration: 1000
                        })
                    }
                })
            }
        } // methods end
    };
</script>

<style lang="less">
    @import "./details";
</style>
