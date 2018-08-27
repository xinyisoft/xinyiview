<template>
    <div>
        <im-tab-bar :current="current" color="#19be6b" :fixed="false" @on-click="handleChange">
            <im-tab-bar-item im-key="homepage" icon="ios-home" current-icon="ios-people" title="Home"></im-tab-bar-item>
            <im-tab-bar-item im-key="group" icon="ios-people" current-icon="ios-home" title="Friends"></im-tab-bar-item>
            <im-tab-bar-item im-key="remind" icon="ios-flask" current-icon="ios-home"  :count="3" title="Notice"></im-tab-bar-item>
            <im-tab-bar-item im-key="mine" icon="document" current-icon="ios-home" dot title="My"></im-tab-bar-item>
        </im-tab-bar>

        <!--自定义主题色-->
        <!--<im-tab-bar :current=" current " color="#f759ab" bindchange="handleChange">-->
            <!--<im-tab-bar-item key="homepage" icon="homepage" current-icon="homepage_fill" title="首页"></im-tab-bar-item>-->
            <!--<im-tab-bar-item key="group" icon="group" current-icon="group_fill" title="朋友"></im-tab-bar-item>-->
            <!--<im-tab-bar-item key="remind" icon="remind" current-icon="remind_fill" title="通知"></im-tab-bar-item>-->
            <!--<im-tab-bar-item key="mine" icon="mine" current-icon="mine_fill" title="我的"></im-tab-bar-item>-->
        <!--</im-tab-bar>-->
    </div>

</template>
<script>


    export default {
        data () {
            return {
                current: 'homepage'

            }
        },
        methods: {

            handleChange ( e ) {
              console.log(e);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
