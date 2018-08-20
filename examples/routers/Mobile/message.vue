<template>
    <div>
        <i-button @click.native="info">显示普通提示</i-button>
        <i-button @click.native="success">显示成功提示</i-button>
        <i-button @click.native="warning">显示警告提示</i-button>
        <i-button @click.native="error">显示错误提示</i-button>
        <i-button @click.native="loading">loading</i-button>
        <i-button @click.native="destroy">销毁提示</i-button>

    </div>
</template>
<script>
    export default {
        methods: {
            info () {
//                this.$Message.info('这是一条普通提示');
                this.$ImMessage.success({
                    content: '这是一条普通提示2',
                    duration: 500,
                    closable: true
                })
            },
            success () {
                this.$ImMessage.success({
                    content: '这是一条成功的提示',
                    duration: 400
                });
            },
            warning () {
                this.$ImMessage.warning('这是一条警告的提示');
            },
            error () {
                this.$ImMessage.error('对方不想说话，并且向你抛出了一个异常');
            },
            loading () {
                this.$ImMessage.loading('对方不想说话，并且向你抛出了一个异常');
            },
            destroy () {
                this.$ImMessage.destroy();
            }
        },
        mounted () {
//            this.$Message.config({
//                top: 50,
//                duration: 3
//            });
        }
    }
</script>
