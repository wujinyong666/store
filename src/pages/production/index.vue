<!--作品集-->
<template>
    <div class="container">
        <div class="content">
            <div class="plat" v-for="(item, index) in productionList" :key="index">
                <img :src="item" alt="">
            </div>
        </div>
    </div>
</template>

<script>
    import productionList from '../../../static/js/production'
    export default {
        data () {
            return {
                productionList: productionList
            };
        },

        methods: {

        },
    };
</script>

<style lang="less">
    @import '../../../static/css/common.less';
    @import '../../../static/css/common';
</style>
