<template>
    <div>
        <Card :bordered="false">
            <p slot="title">No border title</p>
            <p>
                <im-cell-group>
                    <im-cell title="跳转到首页"  url="/pages/dashboard/index" value="详细信息"></im-cell>
                    <im-cell label="附加描述" title="跳转到首页"  url="/pages/dashboard/index" value="详细信息"></im-cell>
                    <im-cell  title="跳转到首页" value="详细信息">
                        <icon type="ios-filing"  slot="icon" />
                    </im-cell>
                </im-cell-group>
            </p>
        </Card>
        <im-panel title="单行">
            <im-cell  title="单行列" ></im-cell>
        </im-panel>

        <im-panel title="跳转">
            <im-cell-group>
                <im-cell title="跳转到首页"  url="/pages/dashboard/index" value="详细信息"></im-cell>
                <im-cell label="附加描述" title="跳转到首页"  url="/pages/dashboard/index" value="详细信息"></im-cell>
                <im-cell  title="跳转到首页" value="详细信息">
                    <icon type="ios-filing"  slot="icon" />
                </im-cell>
            </im-cell-group>
        </im-panel>
        <im-panel title="开关">
            <im-cell-group>
                <im-cell title="开关">
                    <i-switch slot="footer" checked />
                </im-cell>
            </im-cell-group>
        </im-panel>
    </div>

</template>
<script>


    export default {
        data () {
            return {

            }
        },
        methods: {

        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
