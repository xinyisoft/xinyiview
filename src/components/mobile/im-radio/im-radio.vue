<template>
    <im-cell-group>
        <div class="i-class i-radio" v-for="item in options" :key="item.key" @change="handleChange">
            <label class="i-radio-label">
                <im-cell i-class="i-radio-cell">
                    <span :class="[alignCls]">
                      <input
                          v-model="currentValue"
                          :class="['i-radio-input']"
                          type="radio"
                          :disabled="disabled"
                          :value="item.key">
                      <span class="i-radio-core"></span>
                    </span>
                    <div class="i-radio-title">{{item.name}}</div>
                </im-cell>
            </label>
        </div>
    </im-cell-group>
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
                type: Array,
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
        methods:{
            handleChange(e){
                this.$emit('on-change',e)
            }
        }
    }
</script>
