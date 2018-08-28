<template>
    <div :class="['i-class im-mask' , visible ? 'im-mask-show' : '' ]"  @click="handleClickMask">
        <div class="im-mask-header"><slot name="header"></slot></div>
        <div class="im-mask-actions">
            <div class="im-mask-action-item" v-for="(item, index) in actions"  :key="item.name">
                <i-button
                    class="im-mask-btn"
                    @click="handleClickItem"
                    :data-index=" index "
                    :open-type=" item.openType"
                    type="ghost"
                    size="large"
                    long>
                    <div class="im-mask-btn-loading" v-if=" item.loading "></div>
                    <im-icon  v-if=" item.icon " :type=" item.icon " i-class="i-mask-btn-icon"></im-icon>
                    <div class="im-mask-btn-text" :style=" item.color ? 'color: ' + item.color : '' ">{{ item.name }}</div>
                </i-button>
            </div>
        </div>
        <div class="im-mask-cancel" v-if="showCancel">
            <i-button class="im-mask-cancel-btn" type="ghost" size="large" long  @click="handleClickCancel">{{ cancelText }}</i-button>
        </div>
    </div>

</template>

<script>

    export default {
        name: 'ImActionSheet',
        props: {
            visible: {
                type: Boolean,
                value: false
            },
            maskClosable: {
                type: Boolean,
                value: true
            },
            showCancel: {
                type: Boolean,
                value: false
            },
            cancelText: {
                type: String,
                value: '取消',
                default:'取消'
            },
            actions: {
                type: Array,
                value: []
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
                this.$emit('on-click',{value:index})
            },

            handleClickCancel () {
                this.$emit('on-cancel')
            }

        }

    }
</script>
