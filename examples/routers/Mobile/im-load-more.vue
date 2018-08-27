<template>
    <div>
        <im-load-more />
        <im-load-more tip="暂无数据" :loading=" false" />
        <im-load-more :loading="false" />
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

                // $Message({
                //     content: '点击了选项' + index
                // });
            },

            handleClickItem2 () {
                const action = [...this.data.actions2];
                action[0].loading = true;

                this.actions2= action

                // setTimeout(() => {
                //     action[0].loading = false;
                //     this.setData({
                //         visible2: false,
                //         actions2: action
                //     });
                //     $Message({
                //         content: '删除成功！',
                //         type: 'success'
                //     });
                // }, 2000);
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
