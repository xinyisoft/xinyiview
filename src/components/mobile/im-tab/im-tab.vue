<template>
    <div  @click="handleClickItem" :class="['i-class i-tabs-tab',  scroll ? 'i-tabs-tab-scroll' : '' ,  current ? 'i-tabs-tab-current' : '' ]">
        <Badge :dot="dot"  :count="count">
            <div>
                <div v-if=" current " :class="['i-tabs-tab-title i-tabs-tab-title-current']"  :style="{color: activeColor}">{{ title }}</div>
                <div v-else :class="['i-tabs-tab-title' ]">{{ title }}</div>
            </div>
        </Badge>
        <div class="i-tabs-tab-bar" v-if=" current "  :style="barStyle"></div>
    </div>
</template>


<script>
    /**
     *  icon 字体图标-参考图标组件
     *  current-icon  选择图标
     */

    export default {
        name: 'ImTabs',
        data () {
            return {
                lineWidth:2,
                current: false,
                activeColor: '',
                barPosition:'',
                scroll: false
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
        computed:{
            barStyle(){
                const cStyle= {
                    height: this.lineWidth +'px',
                        background: this.activeColor,
                    width:this.customBarWidth
                }
                if(this.barPosition == 'top'){
                    cStyle.top =0;
                }
                return cStyle;
            }
        },
        methods: {

            changeAttr (attrData){
                this.lineWidth = attrData.lineWidth;
                this.activeColor = attrData.activeColor;
                this.barPosition = attrData.barPosition;
                this.customBarWidth = attrData.customBarWidth;
            },
            changeCurrent (current) {
                this.current = current
            },

            changeScroll (scroll) {
                this.scroll = scroll;
            },
            handleClickItem () {
                const parent = this.$parent;
                parent.handleClickItem(this.ImKey);
            }
        }
    }
</script>
