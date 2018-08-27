<template>
    <div :class="['i-class i-drawer' , visible ? 'i-drawer-show' : '' ,  'i-drawer-' + mode ]">
        <div v-if=" mask " class="i-drawer-mask" @click="handleMaskClick"></div>
        <div class="i-drawer-container">
            <slot></slot>
        </div>
    </div>

</template>


<script>
    export default {
        name: 'ImDrawer',
        data () {
            return {

            };
        },
        props: {
            visible: {
                type: Boolean,
                value: false
            },

            mask: {
                type: Boolean,
                value: true
            },

            maskClosable: {
                type: Boolean,
                value: true
            },

            mode: {
                type: String,
                value: 'left' // left right
            }
        },
        mounted: function () {
            this.changeChildCurrent();
        },
        methods: {
            handleMaskClick() {
                if (!this.maskClosable) {
                    return;
                }
                this.$emit('on-close', {});
            }
        },
    }
</script>


