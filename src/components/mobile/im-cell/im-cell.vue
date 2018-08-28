<template>

    <div v-if="url" @click="handleClick" :name="dataIndex"  >
        <router-link  :to="url"    :target="target" :class="['i-class i-cell',isActive?'i-cell-active':'',isLastCell ? 'i-cell-last' : '' ,  url ? 'i-cell-access' : '',IClass]" >
            <div class="i-cell-icon">
                <slot name="icon"></slot>
            </div>
            <div class="i-cell-bd">
                <div v-if="title" class="i-cell-text">{{ title }}</div>
                <div v-if="label" class="i-cell-desc">{{ label }}</div>
                <slot></slot>
            </div>
            <div  class="i-cell-ft">
                <div v-if="value">{{ value }}</div>
                <div v-else>
                    <slot name="footer"></slot>
                </div>
            </div>
        </router-link>
    </div>
    <div v-else @click="handleClick" :name="dataIndex"  :class="['i-class i-cell',isActive?'i-cell-active':'',isLastCell ? 'i-cell-last' : '' ,  url ? 'i-cell-access' : '',IClass]" >
        <div class="i-cell-icon">
            <slot name="icon"></slot>
        </div>
        <div class="i-cell-bd">
            <div v-if="title" class="i-cell-text">{{ title }}</div>
            <div v-if="label" class="i-cell-desc">{{ label }}</div>
            <slot></slot>
        </div>
        <div  class="i-cell-ft">
            <div v-if="value">{{ value }}</div>
            <div v-else>
                <slot name="footer"></slot>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'ImCell',
        props: {
            // 左侧标题
            title: {
                type: String,
            },
            // 标题下方的描述信息
            label: {
                type: String
            },
            name:{
                type: String
            },
            // 右侧内容
            value: {
                type: String
            },
            url: {
                type: String,
                value: '',
                default:'',
            },
            target:{
                type: String,
                value: '',
                default:'_self',
            },
            IClass:{
                type: String,
                value: ''
            }
        },
        data () {
            return {
                dataIndex:0,
                isLastCell: true,
                isActive:false,
            };
        },
        methods: {
            handleClick(e){
                this.isActive = true
                let rData = {}
                rData.value = this.dataIndex;
                this.$emit('on-click',rData);
                if(this.$parent.$options._componentTag == 'im-cell-group'){
                    this.$parent._updateSelected(rData)
                }

            }

        }

    }
</script>
