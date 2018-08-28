<template>
    <div>
        <div style="margin-top: 100px">
            <i-button type="ghost" @click="handleOpen1">一般用法</i-button>
            <i-button type="ghost" @click="handleOpen2">带有提示、异步</i-button>
        </div>
        <im-action-sheet :visible=" visible1 " :actions=" actions1 " cancelText="取消" show-cancel @on-cancel="handleCancel1" @on-click="handleClickItem1" />
        <im-action-sheet :visible=" visible2 " :actions=" actions2 " show-cancel @on-cancel="handleCancel2" @on-click="handleClickItem2"  :mask-closable=" false ">
            <div slot="header" style="padding: 16px">
                <div style="color: #444;font-size: 16px">确定吗？</div>
                <span>删除后无法恢复哦</span>
            </div>
        </im-action-sheet>
    </div>

</template>
<script>
    export default {
        data () {
            return {
                visible1: false,
                visible2: false,
                actions1: [
                    {
                        name: '选项1',
                    },
                    {
                        name: '选项2'
                    },
                    {
                        name: '去分享',
                        icon: 'share',
                        openType: 'share'
                    }
                ],
                actions2: [
                    {
                        name: '删除',
                        color: '#ed3f14'
                    }
                ]
            }
        },
        methods: {

            onShareAppMessage() {
                return {
                    title: 'iView Weapp',
                    imageUrl: 'https://file.iviewui.com/iview-weapp-logo.png'
                };
            },

            handleOpen1 () {
                this.visible1= true
            },

            handleCancel1 () {
                this.visible1=false
            },

            handleOpen2 () {
                this.visible2= true
            },

            handleCancel2 () {
                this.visible2= false

            },

            handleClickItem1 (index) {
                console.log(index);
                // const index = detail.index + 1;
            },

            handleClickItem2 () {
                const action = [...this.actions2];
                action[0].loading = true;

                this.actions2= action

                setTimeout(() => {
                    action[0].loading = false;
                    this.visible2 = false;
                    this.actions2 = action;

                    alert('成功');
                }, 2000);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
