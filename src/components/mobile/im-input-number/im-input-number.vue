<template>
    <div :class="['i-class im-input-number', 'im-input-number-size-'+ size]">
        <div
            :class="['im-input-number-minus' , currentValue <= min ? 'im-input-number-disabled' : '' ]"
            :data-disabled=" currentValue <= min " @click="handleMinus">-</div>
        <input
            v-model="currentValue"
            :class="['im-input-number-text',  min >= max ? 'im-input-number-disabled' : '' ]"
            type="number"
            :disabled=" min >= max "
            @change="handleInputChange" />
        <div :class="['im-input-number-plus',  currentValue >= max ? 'im-input-number-disabled' : '' ]"
             :data-disabled=" currentValue >= max " @click="handlePlus">+</div>
    </div>

</template>


<script>
    export default {
        name: 'ImInputNumber',
        data () {
            return {
                currentValue:this.value,
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
            // small || default || large
            size: String,
            value: {
                type: Number,
                value: 1
            },
            min: {
                type: Number,
                value: -Infinity
            },
            max: {
                type: Number,
                value: Infinity
            },
            step: {
                type: Number,
                value: 1,
                default:1,
            }
        },
        methods: {
            handleInputChange(event) {
                this.$emit('on-change',this.currentValue)
            },
            addNum (num1, num2) {
                let sq1, sq2, m;
                try {
                    sq1 = num1.toString().split('.')[1].length;
                }
                catch (e) {
                    sq1 = 0;
                }
                try {
                    sq2 = num2.toString().split('.')[1].length;
                }
                catch (e) {
                    sq2 = 0;
                }
                m = Math.pow(10, Math.max(sq1, sq2));
                return (Math.round(num1 * m) + Math.round(num2 * m)) / m;
             },
            handleChangeStep(e, type) {

                let  step  = this.step;
                let  value  = this.currentValue;

                if (type === 'minus') {
                    value = this.addNum(value, -step);
                } else if (type === 'plus') {
                    value = this.addNum(value, step);
                }

                if (value < this.min || value > this.max) return null;
                this.currentValue = value;
                this.handleEmit();
            },
            handleMinus(e) {
                this.handleChangeStep(e, 'minus');
            },
            handlePlus(e) {
                this.handleChangeStep(e, 'plus');
            },
            handleEmit(){
                this.$emit('on-change',this.currentValue)
            }
        }
    }
</script>


