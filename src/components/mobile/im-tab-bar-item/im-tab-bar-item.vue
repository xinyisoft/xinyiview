<template>
    <div class="i-class i-tab-bar-item" @click="handleClickItem" >
        <Badge :dot="dot"  :count="count">
            <div>
                <Icon
                    v-if="icon"
                    :color=" current ? currentColor :'' "
                    :type=" current ? currentIcon : icon "
                    size="20"/>
                <image v-else class="i-tab-bar-item-img"  :src=" current ? currentImg : img "></image>
                <div
                    :style="{color: current ? currentColor :'' }"
                    class="i-tab-bar-item-title">{{ title }}</div>
            </div>
        </Badge>
    </div>
</template>


<script>
    /**
     *  icon 字体图标-参考图标组件
     *  current-icon  选择图标
     */

    export default {
        name: 'ImTabBarItem',
        data () {
            return {
                current: false,
                currentColor: ''
            };
        },
        watch: {
            // value(val) {
            //     this.currentValue = val;
            // },
            // currentValue(val) {
            //     this.$emit('input', val);
            // }
        },
        props: {
            icon: {
                type: String,
                value: ''
            },
            currentIcon: {
                type: String,
                value: ''
            },
            img: {
                type: String,
                value: ''
            },
            currentImg: {
                type: String,
                value: ''
            },
            ImKey: {
                type: String,
                value: ''
            },
            title: {
                type: String,
                value: ''
            },
            dot: {
                type: Boolean,
                value: false
            },
            count: {
                type: Number,
                value: 0
            }
        },
        methods: {
            changeCurrent (current) {
                this.current = current;
            },
            changeCurrentColor (currentColor) {
                this.currentColor = currentColor;
            },
            handleClickItem () {
                const parent = this.$parent;
                parent.handleClickItem(this.ImKey)
            }
        }
    }
</script>
