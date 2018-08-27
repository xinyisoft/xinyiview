<template>
    <div>
       <im-scroll-view>
           <ul>
               <li v-for="i in 200" :key="this">
                    你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}} 你是{{i}}
               </li>
           </ul>
       </im-scroll-view>
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
