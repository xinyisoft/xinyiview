<template>
    <div>
        <im-panel title="group-水果">
            <im-checkbox-group :current="current">
                <im-checkbox   v-for="item in fruit"  :checked="false" :position="position"  :value="item.name"></im-checkbox>
            </im-checkbox-group>
        </im-panel>

        <!--<i-button v-bind:change="handleClick()" type="ghost">切换复选框位置</i-button>-->

        <!--<im-panel title="checkbox-动物">-->
            <!--<i-checkbox value="{{animal}}" disabled="{{disabled}}" checked="{{checked}}" bindchange="handleAnimalChange">-->
            <!--</i-checkbox>-->
        <!--</im-panel>-->

        <i-button bindclick="handleDisabled" type="ghost">切换disabled状态</i-button>
    </div>

</template>
<script>


    export default {
        data () {
            return {
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
                position: 'left',
                animal: '熊猫',
                checked: false,
                disabled: false,
            }
        },
        methods: {
            // handleFruitChange({ detail = {} }) {
            //     const index = this.data.current.indexOf(detail.value);
            //     index === -1 ? this.data.current.push(detail.value) : this.data.current.splice(index, 1);
            //     this.setData({
            //         current: this.data.current
            //     });
            // },
            handleClick() {
               this.position = this.position.indexOf('left') !== -1 ? 'right' : 'left';
            },
            handleDisabled() {
                this.setData({
                    disabled: !this.data.disabled
                });
            },
            handleAnimalChange({ detail = {} }) {
                this.setData({
                    checked: detail.current
                });
            },
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
