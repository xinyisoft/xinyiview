<template>
    <div class="im-search-bar">
        <div class="im-search-bar__form" @click="showInput">
            <icon class="im-icon-search_in-box" size="14" type="search"></icon>
            <input v-model="currentValue" @blur="onBlur" @input="onInput" @focus="onFocus" class="im-search-bar__input" placeholder="搜索" type="search">
            <label v-if="isShowInput" class="im-search-bar__label">
                <icon class="im-icon-search" size="14" type="search"></icon>
                <div class="im-search-bar__text">搜索</div>
            </label>
        </div>
        <div class="im-search-bar__cancel-btn" @click="onCancel" :hidden="isShowInput">取消</div>
    </div>
  <!--<div-->
    <!--class="vux-search-box"-->
    <!--:class="{ 'vux-search-fixed':isFixed }"-->
    <!--:style="{ top: isFixed ? top : '', position: fixPosition }">-->
    <!--<div-->
      <!--class="weui-search-bar"-->
      <!--:class="{'weui-search-bar_focusing': !isCancel || currentValue}">-->
      <!--<slot name="left"></slot>-->
      <!--<form class="weui-search-bar__form" @submit.prevent="$emit('on-submit', value)" action=".">-->
        <!--<label-->
          <!--class="vux-search-mask"-->
          <!--@click="touch"-->
          <!--v-show="!isFixed && autoFixed"></label>-->
        <!--<div class="weui-search-bar__box">-->
          <!--<i class="weui-icon-search"></i>-->
          <!--<input-->
            <!--v-model="currentValue"-->
            <!--ref="input"-->
            <!--type="search"-->
            <!--autocomplete="off"-->
            <!--class="weui-search-bar__input"-->
            <!--:placeholder="placeholder"-->
            <!--:required="required"-->
            <!--@focus="onFocus"-->
            <!--@blur="onBlur"-->
            <!--@compositionstart="onComposition($event, 'start')"-->
            <!--@compositionend="onComposition($event, 'end')"-->
            <!--@input="onComposition($event, 'input')"/>-->
          <!--<a-->
            <!--href="javascript:"-->
            <!--class="weui-icon-clear"-->
            <!--@click="clear"-->
            <!--v-show="currentValue"></a>-->
        <!--</div>-->
        <!--<label-->
          <!--class="weui-search-bar__label"-->
          <!--v-show="!isFocus && !value">-->
          <!--<i class="weui-icon-search"></i>-->
          <!--<span>{{ placeholder }}</span>-->
        <!--</label>-->
      <!--</form>-->
      <!--<a-->
        <!--href="javascript:"-->
        <!--class="weui-search-bar__cancel-btn"-->
        <!--@click="cancel">取消-->
      <!--</a>-->
      <!--<slot name="right"></slot>-->
    <!--</div>-->
    <!--<div class="weui-cells vux-search_show" v-show="isFixed">-->
      <!--<slot></slot>-->
      <!--<div-->
        <!--class="weui-cell weui-cell_access"-->
        <!--v-for="item in results"-->
        <!--@click="handleResultClick(item)">-->
        <!--<div class="weui-cell__bd weui-cell_primary">-->
          <!--<p>{{item.title}}</p>-->
        <!--</div>-->
      <!--</div>-->
    <!--</div>-->
  <!--</div>-->
</template>



<script>

export default {
  name: 'ImSearch',
    data () {
        return {
            isShowInput:true,
            currentValue: '',
            isCancel: true,
            isFocus: false,
            isFixed: false
        }
    },
  props: {
    value: {
      type: String,
      default: ''
    },
  },
  created () {
    // if (this.value) {
    //   this.currentValue = this.value
    // }
  },
  computed: {
    // fixPosition () {
    //   if (this.isFixed) {
    //     return this.position === 'absolute' ? 'absolute' : 'fixed'
    //   }
    //   return 'static'
    // }
  },
  methods: {
      showInput (e){
          this.isShowInput = false;
      },
      onCancel(){
          this.isShowInput = true;
          this.currentValue = null;
          this.$emit('on-input', this.currentValue);
      },
      onInput(e){
          this.$emit('on-input', this.currentValue);
      },
      onBlur (e) {
          this.$emit('on-blur',this.currentValue)
      },
      onFocus (e) {
          this.$emit('on-focus',this.currentValue)
      },
  },

  watch: {
    value (val) {
      this.currentValue = val
    }
  }
}
</script>

<style lang="less"></style>
