<template>
    <div>
        基本用法
        <im-panel>
            <im-tabs :line-width="4" scroll-threshold="4" custom-bar-width="50px" active-color="#19be6b" :current=" current " @on-click="handleChange">
                <im-tab im-key="tab1" title="选项1"></im-tab>
                <im-tab im-key="tab2" title="选项2"></im-tab>
                <im-tab im-key="tab3" title="选项3"></im-tab>
                <im-tab im-key="tab4" title="选项4"></im-tab>
                <im-tab im-key="tab5" title="选项5"></im-tab>
                <im-tab im-key="tab6" title="选项6"></im-tab>
                <im-tab im-key="tab7" title="选项7"></im-tab>
            </im-tabs>
        </im-panel>

        <im-panel>
            <im-tabs :line-width="4" bar-position="top" active-color="#19be6b" :current=" current " @on-click="handleChange">
                <im-tab im-key="tab1" title="选项1"></im-tab>
                <im-tab im-key="tab2" title="选项2"></im-tab>
                <im-tab im-key="tab3" title="选项3"></im-tab>
                <im-tab im-key="tab4" title="选项4"></im-tab>
            </im-tabs>
        </im-panel>
        <!--自定义主题色-->

        <!--<i-tabs current="{{ current }}" color="#f759ab" bindchange="handleChange">-->
            <!--<i-tab key="tab1" title="选项1"></i-tab>-->
            <!--<i-tab key="tab2" title="选项2"></i-tab>-->
            <!--<i-tab key="tab3" title="选项3"></i-tab>-->
        <!--</i-tabs>-->

        <!--徽标-->

        <!--<i-tabs current="{{ current }}" bindchange="handleChange">-->
            <!--<i-tab key="tab1" title="选项1" count="3"></i-tab>-->
            <!--<i-tab key="tab2" title="选项2"></i-tab>-->
            <!--<i-tab key="tab3" title="选项3" dot></i-tab>-->
        <!--</i-tabs>-->

        <!--滚动-->

        <!--<i-tabs current="{{ current_scroll }}" scroll bindchange="handleChangeScroll">-->
            <!--<i-tab key="tab1" title="选项1"></i-tab>-->
            <!--<i-tab key="tab2" title="选项2"></i-tab>-->
            <!--<i-tab key="tab3" title="选项3"></i-tab>-->
            <!--<i-tab key="tab4" title="选项4"></i-tab>-->
            <!--<i-tab key="tab5" title="选项5"></i-tab>-->
            <!--<i-tab key="tab6" title="选项6"></i-tab>-->
            <!--<i-tab key="tab7" title="选项7"></i-tab>-->
            <!--<i-tab key="tab8" title="选项8"></i-tab>-->
            <!--<i-tab key="tab9" title="选项9"></i-tab>-->
        <!--</i-tabs>-->
    </div>

</template>
<script>


    export default {
        data () {
            return {
                current: 'tab1',
                current_scroll: 'tab1'

            }
        },
        methods: {

            handleChange (e) {
               console.log(e);
            },

            handleChangeScroll ({ detail }) {
                this.setData({
                    current_scroll: detail.key
                });
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
