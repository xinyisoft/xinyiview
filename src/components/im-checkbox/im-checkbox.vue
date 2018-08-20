<template>
    <div class="i-class i-checkbox" @change="$emit('change', checkboxChange())">
        <im-cell i-class="i-checkbox-cell">
            <label>
                <radio value="value" :checked="checked" :color="[checked?color:'']" :disabled="disabled" :class="['i-checkbox-radio', positionCls]" />
                <div class="i-checkbox-title">{{value}}</div>
            </label>
        </im-cell>
    </div>
</template>


<script>
    const prefixCls = 'i-checkbox';
    export default {
        name: 'ImCheckbox',
        data () {
            return {
                checked:false,
                positionCls: `${prefixCls}-checkbox-left`,
            };
        },
        props: {
            value: {
                type: String,
                value: ''
            },
            disabled: {
                type: Boolean,
                value: false
            },
            color: {
                type: String,
                value: '#2d8cf0'
            },
            position: {
                type: String,
                value: 'left', //left right
            }
        },

        attached() {
            this.setPosition();
        },
        methods: {
            changeCurrent(current) {
                this.checked = current;
            },
            checkboxChange() {
                if (this.disabled) return;
                // const item = { current: !this.checked, value: this.value };
                this.checked =!this.checked;
                // const parent = this.$parent.$parent;

                // parent ? parent.emitEvent(item) : this.triggerEvent('change', item);
            },
            setPosition() {
                this. positionCls = this.position.indexOf('left') !== -1 ? `${prefixCls}-checkbox-left` : `${prefixCls}-checkbox-right`;
            }
        }

    }
</script>


