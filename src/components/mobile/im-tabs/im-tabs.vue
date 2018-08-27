<template>

    <!--<scroll-view wx:if="{{ scroll }}" scroll-x="true" class="i-class i-tabs i-tabs-scroll {{ fixed ? 'i-tabs-fixed' : '' }}"><slot></slot></scroll-view>-->
    <div @click="changeCurrent" :class="['i-class i-tabs',  fixed ? 'i-tabs-fixed' : '' ]"><slot></slot></div>
</template>


<script>
    export default {
        name: 'ImTabs',
        data () {
            return {
                currentV:this.current
                // current: false,
                // currentColor: ''
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
            lineWidth:{
                type: Number,
                value: 2,
            },
            activeColor:{
                type: String,
                value:'#5cadff',
            },
            barPosition:{
                type: String,
                value:'bottom',
            },
            customBarWidth:{
                type: String,
                value:'',
            },
            // scrollThreshold:{
            //     type: Number,
            //     value: 4,
            // },
            current: {
                type: String,
                value: '#2d8cf0',
            },
            color: {
                type: String,
                value: '#2d8cf0'
            },
            scroll: {
                type: Boolean,
                value: false
            },
            fixed: {
                type: Boolean,
                value: false
            }
        },
        mounted: function () {
            this.changeChildCurrent();
        },
        methods: {
            changeChildCurrent (val = this.currentV) {
                let items = this.$children;
                const len = items.length;

                if (len > 0) {
                    let ChildData = {
                        lineWidth:this.lineWidth,
                        activeColor:this.activeColor,
                        barPosition:this.barPosition,
                        customBarWidth:this.customBarWidth,
                        color:this.color
                    };
                    items.forEach(item => {

                        item.changeScroll(this.scroll);
                        item.changeAttr(ChildData);
                        item.changeCurrent(item.ImKey === val);
                    });
                }
            },
            changeCurrent(e){
                this.$emit('on-click',this.currentV);
            },
            handleClickItem (ImKey) {
                this.currentV = ImKey;
                this.changeChildCurrent();
            }
        }
    }
</script>
