<template>
    <a :href="url"  :class="['i-class i-cell',isLastCell ? 'i-cell-last' : '' ,  url ? 'i-cell-access' : '',IClass]">

        <div class="i-cell-icon">
            <slot name="icon"></slot>
        </div>
        <div class="i-cell-bd">
            <div wx:if="title" class="i-cell-text">{{ title }}</div>
            <div wx:if="label" class="i-cell-desc">{{ label }}</div>
            <slot></slot>
        </div>
        <div  class="i-cell-ft">
            <div wx:if="value">{{ value }}</div>
            <div wx:else>
                <slot name="footer"></slot>
            </div>
        </div>

    </a>
</template>

<script>

    export default {
        name: 'ImCell',
        props: {
            // 左侧标题
            title: {
                type: String,
            },
            // 标题下方的描述信息
            label: {
                type: String
            },
            // 右侧内容
            value: {
                type: String
            },
            url: {
                type: String,
                value: ''
            },
            IClass:{
                type: String,
                value: ''
            }
        },
        data () {
            return {
                isLastCell: true
            };
        },
        methods: {


        }

    }
</script>
