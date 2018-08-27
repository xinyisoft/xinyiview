<template>
    <div class="i-class im-grid-item" :style="{width:  width} ">
        <div class="i-class im-grid-icon"><slot name="icon"></slot></div>
        <slot></slot>
        <div v-if="label" class="i-class im-grid-label">{{label}}</div>
    </div>
</template>


<script>
    export default {
        name: 'ImGridItem',
        data () {
            return {
                width:'33.3%'
            };
        },
        props: {
            label: {
                type: String,
                value:''
            },
        },

        methods: {
            changeAttr(attrData){
                this.width = attrData.width;
            }
        },
    }
</script>


