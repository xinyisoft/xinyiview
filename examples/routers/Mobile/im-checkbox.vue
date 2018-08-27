<template>
    <div>
        <im-panel title="right对齐，只能选择2个">
            <im-cell-group>
                <im-checkbox :limit="2"  v-model="checkedValue"  v-for="item in fruit" :key="item.id" align="right"  :options="item.name"></im-checkbox>
            </im-cell-group>
        </im-panel>
        checkedValue:{{checkedValue}}



        <im-panel title="禁用">
            <im-checkbox options="animal" :disabled="disabled"></im-checkbox>
        </im-panel>
    </div>

</template>
<script>
    export default {
        data () {
            return {
                checkedValue:['香蕉','苹果'],
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
                current: ['苹果', '葡萄'],
                align: 'right',
                animal: '熊猫',
                checked: false,
                disabled: true,
            }
        },
        created:{

        },
        methods: {

        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
