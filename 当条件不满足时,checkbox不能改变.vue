<template>
  <div>
    <input type="checkbox" v-model="checkValue" @click="intoWatch()"/> : 
    <input type="text" name="" v-model="checkValue">
    <br>
    校验规则:rules值为1能勾上 ,rules值为0不能勾上
    <input type="text" name="" v-model="rules"/>
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
      rules: '0',
      flag: 0,
      checkValue: false
    }
  },
  watch: {
    checkValue: function () {
      if (this.flag === 1) {
        if (this.rules !== '1') {
          this.checkValue = !this.checkValue // watch checkValue改变后当条件不满足时,重置为原来的状态. 为了防止watch checkValue死循环,增加flag = 1
        }
        this.flag = 0
      }
    }
  },
  methods: {
    intoWatch: function () {
      this.flag = 1
    }
  }
}
</script>
