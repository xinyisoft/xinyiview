<template>
    <div>
        <im-panel title="基础用法">
            <im-input :value=" value1" title="收货人" @on-input="changInput3" @on-blur="changInput"  autofocus placeholder="名字" />
            <im-input :value=" value2 " type="number"  title="联系电话" placeholder="请输入手机号" />
            <im-input :value=" value3 " type="textarea" title="详细地址" placeholder="请输入详细地址(最多50字)" :maxlength="50" />
            <im-input :value=" value4 " title="用户信息" disabled />
        </im-panel>

        <im-panel title="无标题输入框">
            <im-input :value=" value5 " placeholder="请输入收货人姓名" />
        </im-panel>

        <im-panel title="圆角输入框">
            <im-input value=" value6 " type="number" right title="消费总额" mode="wrapped" placeholder="询问收银员后输入" />
            <im-input value=" value7 " type="number" right error title="不参与优惠金额" mode="wrapped" placeholder="询问收银员后输入" />
        </im-panel>
    </div>

</template>
<script>


    export default {
        data () {
            return {
                value1: '',
                value2: '',
                value3: '',
                value4: '输入框已禁用',
                value5: '',
                value6: '',
                value7: ''
            }
        },
        methods: {
            changInput(e){
                console.log(e.target.value);
            },
            changInput2(e){
                console.log(e.target.value);
            },
            changInput3(e){
                console.log(e.target.value);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
