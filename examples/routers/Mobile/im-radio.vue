<template>
    <div>

        <im-panel title="right对齐">
            <im-cell-group>
                <im-radio v-model="radioItem" v-for="item in fruit" :key="item.id" align="right"  :options="item.name"></im-radio>
            </im-cell-group>
        </im-panel>
        radio: {{radioItem}}
        <!--<im-panel title="left对齐">-->
            <!--<im-radio-group :current="current">-->
                <!--<im-radio   v-for="item in fruit" :key="item.id"  align="left"  :value="item.name"></im-radio>-->
            <!--</im-radio-group>-->
        <!--</im-panel>-->

        <!--<im-panel title="checkbox-动物">-->
            <!--<im-radio value="animal" :disabled="disabled"></im-radio>-->
        <!--</im-panel>-->
    </div>

</template>
<script>
    export default {
        data () {
            return {
                radioItem:'苹果',
                fruit: [{
                    id: 1,
                    name: '香蕉',
                }, {
                    id: 2,
                    name: '苹果'
                }, {
                    id: 3,
                    name: '西瓜'
                }, {
                    id: 4,
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
            headlRadio(){
                console.log();
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
