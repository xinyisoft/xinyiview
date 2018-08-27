<template>
    <div class="im-search-bar">
        <div class="im-search-bar__form" @click="showInput">
            <icon class="im-icon-search_in-box" size="14" type="search"></icon>
            <input ref="searchInput" v-model="currentValue"  @blur="onBlur" @input="onInput" @focus="onFocus" class="im-search-bar__input" placeholder="搜索" type="search">
            <label v-if="isShowInput" class="im-search-bar__label">
                <icon class="im-icon-search" size="14" type="search"></icon>
                <div class="im-search-bar__text">搜索</div>
            </label>
        </div>
        <div class="im-search-bar__cancel-btn" @click="onCancel" :hidden="isShowInput">取消</div>
    </div>
</template>



<script>

export default {
  name: 'ImSearch',
    data () {
        return {
            isShowInput:true,
            currentValue: '',
        }
    },
  props: {
    value: {
      type: String,
      default: ''
    },
  },
  created () {

  },
  computed: {

  },
  methods: {
      showInput (e){
          this.$refs.searchInput.focus();
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
          if( this.currentValue.length == 0){
              this.isShowInput = true;
          }
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
