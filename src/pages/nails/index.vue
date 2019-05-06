<!--做美甲-->
<template>
    <div class="container">
        <div class="content">
            <div class="plat" v-for="(item, index) in nailsList" :key="index" @click="nailsDetails(item)">
                <img :src="item.coverUrl" alt="">
                <div class="nails-name">
                    <h3>{{ item.name }}</h3>
                    <span>{{ item.part }}</span>
                </div>
                <div class="do-it">
                    做这款
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import nailsList from '../../../static/js/nails'
    export default {
        data () {
            return {
                nailsList: nailsList
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
    @import '../../../static/css/common';
</style>
