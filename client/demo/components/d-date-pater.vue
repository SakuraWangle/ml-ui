<template>
  <div class="dd-body">
    <d-head :back="true" title="DatePater"></d-head>
    <div class="dd-warp">
      <div class="warp-ctt">
        <div class="dd-label">
          <ml-button @click="doClick(0)">默认(yyyy-MM-dd) 值 {{date}}</ml-button>
          <ml-date-pater @on-confirm="doConfirm" @on-cancel="doClose" ref="datePater0" v-model="date"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(1)">格式 hh:mm 值 {{date1}}</ml-button>
          <ml-date-pater format="hh:mm" ref="datePater1" v-model="date1"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(2)">格式 hh:mm:ss 值 {{date2}}</ml-button>
          <ml-date-pater format="hh:mm:ss" ref="datePater2" v-model="date2"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(3)">格式 yyyy 值 {{date3}}</ml-button>
          <ml-date-pater format="yyyy" ref="datePater3" v-model="date3"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(4)">格式 yyyy-MM 值 {{date4}}</ml-button>
          <ml-date-pater format="yyyy-MM" ref="datePater4" v-model="date4"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(5)">格式 MM-dd 值 {{date5}}</ml-button>
          <ml-date-pater format="MM-dd" ref="datePater5" v-model="date5"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(6)">格式 yyyy-MM-dd hh:mm</ml-button>
          <div class="pater-value">值 {{date6}}</div>
          <ml-date-pater format="yyyy-MM-dd hh:mm" ref="datePater6" v-model="date6"></ml-date-pater>
        </div>
        <div class="dd-label">
          <ml-button @click="doClick(7)">格式 yyyy-MM-dd hh:mm:ss</ml-button>
          <div class="pater-value">值 {{date7}}</div>
          <ml-date-pater format="yyyy-MM-dd hh:mm:ss" ref="datePater7" v-model="date7"></ml-date-pater>
        </div>
      </div>
    </div>
  </div>
</template>
<script type="text/babel">
  export default {
    data() {
      return {
        date: '',
        date1: '',
        date2: '',
        date3: '',
        date4: '',
        date5: '',
        date6: '',
        date7: '',
      }
    },
    methods: {
      doClick(index) {
        this.$refs[`datePater${index}`].doOpen()
      },
      doConfirm(date) {
        this.$message.success({ message: date })
      },
      doClose() {
        this.$message.warning({ message: '取消了' })
      },
    }
  }
</script>
<style lang="stylus" scoped>
  .dd-label {
    padding-bottom: 5px;
  }

  .pater-value {
    padding-top: 5px;
  }
</style>