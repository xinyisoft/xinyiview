<template>
    <div>

        <im-panel title="基础用法">
            <im-search @on-input="onInput" @on-blur="onBlur" @on-focus="onFocus"></im-search>
        </im-panel>
    </div>

</template>
<script>


    export default {
        data () {
            return {
                value1: 5,
                value2: 2.2,
            }
        },
        methods: {
            onInput(e){
                console.log(e);
            },
            onBlur(e){
                console.log(e);
            },
            onFocus(e){
                console.log(e);
            },
            handleChange1(e){
                console.log(e);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
