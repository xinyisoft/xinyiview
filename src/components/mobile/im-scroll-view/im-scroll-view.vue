<template>
    <div :class="['i-class','i-scroll-view']" >
        <div class="i-scroll-view-content">
            <slot></slot>
        </div>
    </div>
</template>


<script>
    export default {
        name: 'ImScrollView',
        data () {
            return {

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

        },

        mounted: function () {

        },
        methods: {

        }
    }
</script>
