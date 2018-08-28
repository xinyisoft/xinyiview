<template>
    <div>

        <im-panel title="right对齐">
                <im-radio v-model="radioItem"  align="right"  @on-change="handleChange" :options="fruit"></im-radio>

        </im-panel>
        radio: {{radioItem}}
        <im-panel title="left对齐">
            <im-radio   align="left" :options="fruit" ></im-radio>
        </im-panel>

        <im-panel title="禁用">
            <im-radio :options="fruit" :disabled="disabled"></im-radio>
        </im-panel>
    </div>

</template>
<script>
    export default {
        data () {
            return {
                radioItem:'1',
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
                current: '苹果',
                align: 'right',
                animal: '熊猫',
                checked: false,
                disabled: true,
            }
        },
        methods: {
            handleChange(e){
                console.log(e);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
