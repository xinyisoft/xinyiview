<template>
    <div>
        <im-panel title="基础用法">
            <div style="padding: 16px">
                <im-input-number :value="value1" :min="0" :max="100" :step="1" @on-change="handleChange1" />
            </div>
        </im-panel>

        <im-panel title="小数">
            <div style="padding: 16px">
                <im-input-number :value="value2" :min="0" :max="100" :step="0.2" bindchange="handleChange2" />
            </div>
        </im-panel>
    </div>

</template>
<script>


    export default {
        data () {
            return {
                value1: 5,
                value2: 2.2,

            }
        },
        methods: {

            handleChange1(e){
                console.log(e);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
