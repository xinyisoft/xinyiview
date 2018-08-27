<template>
    <div :class="['i-class i-tab-bar',  fixed ? 'i-tab-bar-fixed' : '' ]" @click="changeCurrent">
        <slot></slot>
        <!--<div class="i-tab-bar-list">-->
            <!--&lt;!&ndash;<div class="i-tab-bar-layer" v-for="item in list " :key="item.key"  :data-key=" item.key " @click="handleClickItem"  :style="{width:  100 / list.length +'%'}"></div>&ndash;&gt;-->
        <!--</div>-->
    </div>
</template>


<script>
    export default {
        name: 'ImTabBar',
        data () {
            return {
                currentV:this.current
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
            current: {
                type: String,
                value: '',
            },
            color: {
                type: String,
                value: ''
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

                    items.forEach(item => {
                        item.changeCurrent(item.ImKey === val);
                        item.changeCurrentColor(this.color);
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
