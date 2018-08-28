<template>
    <div :class="['i-class i-cell-group',hover?'i-cell-group-hover':'',active?'i-cell-group-active':'']">
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
        props: {
            hover:{
                type:Boolean,
                value:false,
            },
            active:{
                type:Boolean,
                value:false,
            },
            // 右侧内容
            value: {
                type: String
            },
        },
        methods: {
            _updateIsLastCell() {
                let cells = this.$children;
                const len = cells.length;

                if (len > 0) {
                    let lastIndex = len - 1;

                    cells.forEach((cell, index) => {
                        if(!cell.$options.propsData.name){
                            cell.dataIndex = index+1;
                        }else{
                            cell.dataIndex = cell.$options.propsData.name
                        }

                        if(cell.$options.propsData.name == this.value){
                            cell.isActive = true;
                        }else{
                            cell.isActive = false;
                        }

                        cell.isLastCell  =   index === lastIndex
                    });
                }
            },
            _updateSelected(data) {
                let cells = this.$children;
                const len = cells.length;
                if (len > 0) {
                    cells.forEach((cell, index) => {
                        if(data.value == cell.dataIndex){
                            cell.isActive = true;
                        }else{
                            cell.isActive = false;
                        }
                    });
                }
                this.$emit('on-click',data)
            }
        },
        mounted: function () {
           this._updateIsLastCell();
        }

    }
</script>
