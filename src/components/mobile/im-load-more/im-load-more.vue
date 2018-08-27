<template>
    <div :class="['i-class i-load-more',  loading ? '' : 'i-load-more-line' ]">
        <div class="i-load-more-loading" v-if=" loading "></div>
        <div class="i-load-more-tip">
            <div v-if=" tip !== '' ">{{ tip }}</div>
            <div v-else-if=" tip === '' && loading ">正在加载</div>
            <div class="i-load-more-empty" v-else></div>
        </div>
    </div>

</template>

<script>

    export default {
        name: 'ImLoadMore',
        props: {
            loading: {
                type: Boolean,
                value: true
            },
            tip: {
                type: String,
                value: '',
                default:'',
            }
        },
        data () {
            return {
                isLastCell: true
            };
        },
        methods: {
            handleClickMask () {
                if (!this.maskClosable) return;
                this.handleClickCancel();
            },

            handleClickItem ({currentTarget}) {
                const dataset = currentTarget.dataset || {};
                const { index } = dataset;
                this.$emit('on-click',index)
            },

            handleClickCancel () {
                this.$emit('on-cancel')
            }

        }

    }
</script>
