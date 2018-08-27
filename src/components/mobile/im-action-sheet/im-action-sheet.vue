<template>
    <div>
    <div :class="['i-as-mask i-class-mask' , visible ? 'i-as-mask-show' : '' ]"  @click="handleClickMask"></div>
    <div :class="['i-class i-as' , visible ? 'i-as-show' : '' ]">
        <div class="i-as-header i-class-header"><slot name="header"></slot></div>
        <div class="i-as-actions">
            <div class="i-as-action-item" v-for="(item, index) in actions"  :key="item.name">
                <i-button
                    @click="handleClickItem"
                    :data-index=" index "
                    :open-type=" item.openType"
                    type="ghost"
                    size="large"
                    long>
                    <div class="i-as-btn-loading" v-if=" item.loading "></div>
                    <Icon  v-if=" item.icon " :type=" item.icon " i-class="i-as-btn-icon"></Icon>
                    <div class="i-as-btn-text" :style=" item.color ? 'color: ' + item.color : '' ">{{ item.name }}</div>
                </i-button>
            </div>
        </div>
        <div class="i-as-cancel" v-if="showCancel">
            <i-button i-class="i-as-cancel-btn" type="ghost" size="large" long  @click="handleClickCancel">{{ cancelText }}</i-button>
        </div>
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
                this.$emit('on-click',index)
            },

            handleClickCancel () {
                this.$emit('on-cancel')
            }

        }

    }
</script>
