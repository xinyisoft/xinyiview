<template>
    <im-cell-group>
    <div class="i-class i-checkbox" @change="handleChange">
        <label class="i-checkbox-label" v-for="item in options" :key="item.key">
            <im-cell i-class="i-checkbox-cell" >
                <span :class="[alignCls]">
                  <input
                      v-model="currentValue"
                      :class="['i-checkbox-input']"
                      type="checkbox"
                      :disabled="disabled"
                      :value="item.key">
                  <span class="i-checkbox-core"></span>
                </span>
                <div class="i-checkbox-title">{{item.name}}</div>
            </im-cell>
        </label>
    </div>
    </im-cell-group>
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
                type: Array,
                value:[],
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
        methods:{
            handleChange(e){
                this.$emit('on-change',e);
            }
        }
    }
</script>


