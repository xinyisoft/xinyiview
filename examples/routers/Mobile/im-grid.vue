<template>
    <div>
        <im-grid :cols="6">
            <im-grid-item  label="Grid" v-for="i in 9" :key="i">
                <div slot="icon">{{i}} </div>
            </im-grid-item>
        </im-grid>
    </div>

</template>
<script>


    export default {
        data () {
            return {
                current: 'tab1',
                current_scroll: 'tab1'
            }
        },
        methods: {

            handleChange (e) {
               console.log(e);
            },

            handleChangeScroll ({ detail }) {
                this.setData({
                    current_scroll: detail.key
                });
            }
        }
    }
</script>

<style lang="less">
    /*body{background: #ededed !important;}*/
</style>
