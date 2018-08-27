<template>
    <div :class="['i-class i-cell im-input', error ? 'im-input-error' : '' ,  mode === 'wrapped' ? 'im-input-wrapped' : '' ]">
        <div v-if=" title " class="i-cell-hd im-input-title">{{ title }}</div>
        <textarea
            v-if=" type === 'textarea' "
            auto-height
            :disabled=" disabled "
            :focus=" autofocus "
            :value=" value "
            :placeholder=" placeholder "
            :maxlength=" maxlength "
            :class="['im-input-input i-cell-bd',  right ? 'im-input-input-right' : '' ]"
            placeholder-class="im-input-placeholder"
            @input="handleInput"
            @focus="handleInputFocus"
            @blur="handleInputBlur"
        ></textarea>
        <input
            v-else
            :type=" type "
            :disabled=" disabled "
            :focus=" autofocus "
            :value=" value "
            :placeholder=" placeholder "
            :maxlength=" maxlength "
            :class="['im-input-input i-cell-bd',  right ? 'im-input-input-right' : '' ]"
            placeholder-class="im-input-placeholder"
            @input="handleInput"
            @focus="handleInputFocus"
            @blur="handleInputBlur"
        />
    </div>

</template>


<script>
    export default {
        name: 'ImInput',
        data () {
            return {

            };
        },
        props: {
            value: {
                type: String
            },
            title: {
                type: String
            },
            // text || textarea || password || number
            type: {
                type: String,
                value: 'text'
            },
            disabled: {
                type: Boolean,
                value: false
            },
            placeholder: {
                type: String,
                value: ''
            },
            autofocus: {
                type: Boolean,
                value: false
            },
            mode: {
                type: String,
                value: 'normal'
            },
            right: {
                type: Boolean,
                value: false
            },
            error: {
                type: Boolean,
                value: false
            },
            maxlength: {
                type: Number
            }
        },

        methods: {
            handleInput(event) {
                this.$emit('on-input',event)
            },

            handleInputFocus(event) {
                this.$emit('on-focus',event)
            },
            handleInputBlur(event) {
                this.$emit('on-blur',event)
            }
        }
    }
</script>


