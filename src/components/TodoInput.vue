<template>

  <div class="wrap">
    <div class="btWrap">
      <div class="bt" :class="{ plus:isChange, check:!isChange }" @click="onClick">{{sign}}</div>
    </div>
    <div :class="{inputWrap:!isChange}">
      <input class="newItem" ref="todoInput" :disabled="isChange" >
    </div>
  </div>

</template>

<script>

export default {

  data() {
    return{
      sign:'+',
      isChange:'true',
    }
  },

  updated() {
    this.focusInput();
    this.inputReset();
  },

  methods: {
    focusInput: function() {
      console.log("change");
      this.$refs.todoInput.focus();
    },
    onClick: function() {
      if(this.sign == '+'){
        this.isChange=!this.isChange;
        this.sign = '✓';
      }
      else {
        if(this.$refs.todoInput.value == ''){
          alert("취소되었습니다!");
        }
        else {
          alert("입력되었습니다!");
        }
        this.isChange=!this.isChange;
        this.sign='+'
      }
    },
    inputReset: function() {
        this.$refs.todoInput.value = '';
    },
  }

};

</script>

<style scoped>
.wrap {
  width:100%;
}
.btWrap {
  position: relative;
  left: 460px;
  bottom: 4ex;
}
.bt {
  z-index: 2;
  text-align: center;
  font-size: 40px;
  border-radius: 30px;
  width: 60px;
  height: 60px;
}
.plus {
  border: none;
  color: white;
  background-color:rgb(65, 250, 188);
}
.check {
  box-shadow: 0 0 10px;
  background-color: white;
  color: rgb(65, 250, 188);
}
.newItem {
  font-size: 25px;
  margin-left: 42px;
  margin-right: 46px;
  margin-bottom: 20px;
  width: 500px;
  height: 50px;
  border: none;
  background-color: white;
  word-break: break-word;
}

.newItem:focus{
  outline: none;
  background-color: rgb(250,250,250);
  padding-left: 10px;
}
.inputWrap{
  border-bottom: 1px solid rgb(190,190,190);
}

</style>