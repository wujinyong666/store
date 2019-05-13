<!--优惠活动-->
<template>
    <div class="activity">
        <div class="plate" v-for="(item, index) in activityList" :key="index">
            <img :src="item.url" alt="">
        </div>
    </div>
</template>

<script>
    export default {
        name: "activity",
        data () {
            return {
                activityList: [
                    {
                        id: 1,
                        activityName: '活动名称1',
                        url: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557760871535&di=619c8b277ecae38afe8e64db50eb96ca&imgtype=0&src=http%3A%2F%2Fpic.90sjimg.com%2Fdesign%2F00%2F39%2F17%2F34%2F572035ee2599d.jpg',
                    },
                    {
                        id: 2,
                        activityName: '活动名称2',
                        url: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557760871535&di=06c41771390a260a7ba13cdae07e4253&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01eda75938c474a8012193a34f73f4.jpg',
                    },
                ]
            }
        },
    }
</script>

<style lang="less">
    @import '../../../static/css/common';
    @import "activity";
</style>
