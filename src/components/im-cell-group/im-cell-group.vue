<template>
    <div class="i-class i-cell-group">
        <slot></slot>
    </div>
</template>


<script>
    export default {
        name: 'ImCellGroup',
        data () {
            return {

            };
        },
        methods: {
            _updateIsLastCell() {
                let cells = this.$children;
                const len = cells.length;

                if (len > 0) {
                    let lastIndex = len - 1;

                    cells.forEach((cell, index) => {
                        cell.isLastCell  =   index === lastIndex
                    });
                }
            }
        },
        mounted: function () {
           this._updateIsLastCell();
        }

    }
</script>
