<template>
    <div class="i-class i-radio">
        <im-cell i-class="i-radio-cell">
            <label class="i-radio-label">
                <span :class="[alignCls]">
                  <input
                      v-model="currentValue"
                      :class="['i-radio-input']"
                      type="radio"
                      :disabled="disabled"
                      :value="options">
                  <span class="i-radio-core"></span>
                </span>
                <div class="i-radio-title">{{options}}</div>
            </label>
        </im-cell>
    </div>
</template>


<script>
    const prefixCls = 'i-radio';
    export default {
        name: 'ImRadio',
        data () {
            return {
                currentValue: this.value,
                alignCls: `${prefixCls}-radio-${this.align}`,
            };
        },
        watch: {
            value(val) {
                this.currentValue = val;
            },
            currentValue(val) {
                this.$emit('input', val);
            }
        },
        props: {
            value: {
                type: String,
            },
            options:{
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
            align: {
                type: String,
                value: 'left', //left right
            }
        },
    }
</script>
