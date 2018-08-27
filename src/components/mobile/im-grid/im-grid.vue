<template>
    <div class="i-class i-grid"><slot></slot></div>

</template>


<script>
    export default {
        name: 'ImGrid',
        data () {
            return {

            };
        },
        props: {
            cols: {
                type: Number,
                value:3,
                default:3,
            },
        },
        mounted: function () {
            this.changeChildCurrent();
        },
        methods: {
            changeChildCurrent (val = this.currentV) {
                let items = this.$children;
                const len = items.length;
                if (len > 0) {
                    console.log(this.cols);
                    let attrData = {
                      width:parseFloat(100 / parseFloat(this.cols)) + '%',
                    };
                    items.forEach(item => {
                        item.changeAttr(attrData);
                        // item.changeCurrent(item.ImKey === val);
                    });
                }

            },
        },
    }
</script>


