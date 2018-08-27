<style lang="less">
    @import "../src/styles/index.less";
</style>
<style lang="less" scoped>
nav {
    margin-bottom: 40px;
    ul {
        display: flex; flex-wrap: wrap;
        border-bottom: 1px solid #2b85e4;
        padding: 20px;
    }
    li {
        display: inline-block;
        width: 20%;
    }
}
.container{ padding: 10px 40px 0; }
.v-link-active { color: #bbb; }
</style>
<template>
    <div class="container">
        <nav>
            <ul>
                <li><router-link to="/layout">Layout</router-link></li>
                <li><router-link to="/affix">Affix</router-link></li>
                <li><router-link to="/grid">Grid</router-link></li>
                <li><router-link to="/button">Button</router-link></li>
                <li><router-link to="/input">Input</router-link></li>
                <li><router-link to="/radio">Radio</router-link></li>
                <li><router-link to="/checkbox">Checkbox</router-link></li>
                <li><router-link to="/steps">Steps</router-link></li>
                <li><router-link to="/timeline">Timeline</router-link></li>
                <li><router-link to="/switch">Switch</router-link></li>
                <li><router-link to="/alert">Alert</router-link></li>
                <li><router-link to="/badge">Badge</router-link></li>
                <li><router-link to="/tag">Tag</router-link></li>
                <li><router-link to="/input-number">InputNumber</router-link></li>
                <li><router-link to="/progress">Progress</router-link></li>
                <li><router-link to="/upload">Upload</router-link></li>
                <li><router-link to="/collapse">Collapse</router-link></li>
                <li><router-link to="/carousel">Carousel</router-link></li>
                <li><router-link to="/card">Card</router-link></li>
                <li><router-link to="/tree">Tree</router-link></li>
                <li><router-link to="/rate">Rate</router-link></li>
                <li><router-link to="/circle">Circle</router-link></li>
                <li><router-link to="/tabs">Tabs</router-link></li>
                <li><router-link to="/tooltip">Tooltip</router-link></li>
                <li><router-link to="/poptip">Poptip</router-link></li>
                <li><router-link to="/slider">Slider</router-link></li>
                <li><router-link to="/dropdown">Dropdown</router-link></li>
                <li><router-link to="/breadcrumb">Breadcrumb</router-link></li>
                <li><router-link to="/menu">Menu</router-link></li>
                <li><router-link to="/spin">Spin</router-link></li>
                <li><router-link to="/cascader">Cascader</router-link></li>
                <li><router-link to="/select">Select</router-link></li>
                <li><router-link to="/backtop">Backtop</router-link></li>
                <li><router-link to="/page">Page</router-link></li>
                <li><router-link to="/transfer">Transfer</router-link></li>
                <li><router-link to="/date">Date</router-link></li>
                <li><router-link to="/form">Form</router-link></li>
                <li><router-link to="/table">Table</router-link></li>
                <li><router-link to="/loading-bar">LoadingBar</router-link></li>
                <li><router-link to="/modal">Modal</router-link></li>
                <li><router-link to="/message">Message</router-link></li>
                <li><router-link to="/notice">Notice</router-link></li>
                <li><router-link to="/avatar">Avatar</router-link></li>
                <li><router-link to="/color-picker">ColorPicker</router-link></li>
                <li><router-link to="/auto-complete">AutoComplete</router-link></li>
                <li><router-link to="/scroll">Scroll</router-link></li>
            </ul>
            <ul>
                <li><router-link to="/Mobile/message">Mobile message</router-link></li>
                <li><router-link to="/im-list">im-list列表</router-link></li>
                <li><router-link to="/im-checkbox">im-checkbox复选</router-link></li>
                <li><router-link to="/im-radio">im-radio单选</router-link></li>
                <li><router-link to="/im-input">im-input输入框</router-link></li>
                <li><router-link to="/im-input-number">im-input-number数字输入框</router-link></li>
                <li><router-link to="/im-search">im-search 搜索输入框</router-link></li>
                <li><router-link to="/im-tab-bar">im-tab-bar标签栏</router-link></li>
                <li><router-link to="/im-tabs">im-tabs标签页</router-link></li>
                <li><router-link to="/im-grid">im-grid 宫格</router-link></li>
                <li><router-link to="/im-scroll-view">im-scroll-view 滚动视图</router-link></li>
                <li><router-link to="/im-picker">im-picker 选择器</router-link></li>
                <li><router-link to="/im-swipeout">im-swipeout 选择器</router-link></li>
                <li><router-link to="/im-action-sheet">im-action-sheet 动作面板</router-link></li>
                <li><router-link to="/im-load-more">im-load-more 动作面板</router-link></li>
                <li><router-link to="/im-drawer">im-drawer 侧滑插件</router-link></li>
                <li><router-link to="/im-icon">im-drawer 图标</router-link></li>
            </ul>
        </nav>
        <router-view></router-view>
    </div>
</template>
<script>
    module.exports = {
        data: function() {
            return {

            }
        },
        mounted: function() {

        },
        beforeDestroy: function() {

        },
        methods: {

        }
    }
</script>
