<template>
    <div>
        <im-icon type="camera-retro"></im-icon>
    </div>

</template>
<script>


    export default {
        data () {
            return {
                showLeft1: false,
                showLeft2: false,
                showRight1: false,
                showRigh2: false,
            }
        },
        methods: {

            toggleLeft1() {
                this.setData({
                    showLeft1: !this.data.showLeft1
                });
            },
            toggleLeft2() {
                this.setData({
                    showLeft2: !this.data.showLeft2
                });
            },
            toggleRight1() {
                this.setData({
                    showRight1: !this.data.showRight1
                });
            },
            toggleRight2() {
                this.setData({
                    showRight2: !this.data.showRight2
                });
            }
        }
    }
</script>

<style lang="less">
    /*body{background: #ededed !important;}*/
</style>
