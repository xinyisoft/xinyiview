<template>
    <im-cell-group>
        <slot></slot>
    </im-cell-group>

</template>


<script>
    export default {
        name: 'ImCheckboxGroup',
        data () {
            return {

            };
        },
        props: {
            current: {
                type: Array,
                value: [],
            },
        },
        methods: {
            changeCurrent(val = this.current) {
                let items = this.$children[0].$children;

                const len = items.length;

                if (len > 0) {
                    items.forEach(item => {
                        item.changeCurrent(val.indexOf(item.value) !== -1);
                    });
                }
            },
            emitEvent(current) {
                this.triggerEvent('change', current);
            }
        },
        mounted: function () {
           this.changeCurrent();
        }

    }
</script>
