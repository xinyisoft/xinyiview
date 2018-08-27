<template>
    <i :class="classes" :style="styles" @click="handleClick"></i>
</template>
<script>
    const prefixCls = 'fa';

    export default {
        name: 'ImIcon',
        props: {
            type: String,
            size: [Number, String],
            color: String
        },
        computed: {
            classes () {
                return `${prefixCls} ${prefixCls}-${this.type}`;
            },
            styles () {
                let style = {};

                if (this.size) {
                    style['font-size'] = `${this.size}px`;
                }

                if (this.color) {
                    style.color = this.color;
                }

                return style;
            }
        },
        methods: {
            handleClick (event) {
                this.$emit('click', event);
            }
        }
    };
</script>
