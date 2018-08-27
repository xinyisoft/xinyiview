<template>
    <div class="i-class i-panel">
        <div wx:if=" title " :class="['i-panel-title', hideTop ? 'i-panel-title-hide-top' : '' ]">{{ title }}</div>
        <div :class="['i-panel-content',  hideBorder ? 'i-panel-without-border' : '' ]"><slot></slot></div>
    </div>

</template>


<script>
    export default {
        name: 'ImPanel',
        data () {
            return {

            };
        },
        props: {
            title: {
                type: String,
                value: ''
            },
            // 标题顶部距离
            hideTop: {
                type: Boolean,
                value: false
            },
            hideBorder: {
                type: Boolean,
                value: false
            }
        },
        methods: {
        }

    }
</script>
