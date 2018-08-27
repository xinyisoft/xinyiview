<template>
    <div class="i-class i-checkbox">
        <im-cell i-class="i-checkbox-cell">
            <label class="i-checkbox-label">
                <span :class="[alignCls]">
                  <input
                      v-model="currentValue"
                      :class="['i-checkbox-input']"
                      type="checkbox"
                      :disabled="disabled"
                      :value="options">
                  <span class="i-checkbox-core"></span>
                </span>
                <div class="i-checkbox-title">{{options}}</div>
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
                currentValue: this.value,
                alignCls: `${prefixCls}-checkbox-${this.align}`,
            };
        },
        watch: {
            value(val) {
                this.currentValue = val;
            },
            currentValue(val) {
                if ( val.length > this.limit) val.pop();
                this.$emit('input', val);
            }
        },
        props: {
            options: {
                type: String,
                value:'',
            },
            value: Array,
            disabled: {
                type: Boolean,
                value: false
            },
            color: {
                type: String,
                value: '#2d8cf0'
            },
            limit: {
                type: Number,
                value: 0
            },
            align: {
                type: String,
                value: 'left', //left right
            }
        },
    }
</script>


