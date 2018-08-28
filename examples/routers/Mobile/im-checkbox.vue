<template>
    <div>
        <im-panel title="right对齐，只能选择2个">
            <im-checkbox :limit="2"  v-model="checkedValue" @on-change="headlchange"  align="right"  :options="fruit"></im-checkbox>
        </im-panel>
        checkedValue:{{checkedValue}}

        <im-panel title="禁用">
            <im-checkbox :options="[{key:'animal',name:'animal'}]" :disabled="disabled"></im-checkbox>
        </im-panel>
    </div>

</template>
<script>
    export default {
        data () {
            return {
                checkedValue:['1','2','4'],
                fruit: [{
                    key: 1,
                    name: '香蕉',
                }, {
                    key: 2,
                    name: '苹果'
                }, {
                    key: 3,
                    name: '西瓜'
                }, {
                    key: 4,
                    name: '葡萄',
                }],
                current: ['苹果', '葡萄'],
                align: 'right',
                animal: '熊猫',
                checked: false,
                disabled: true,
            }
        },

        methods: {
            headlchange(e){
                console.log(e);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
