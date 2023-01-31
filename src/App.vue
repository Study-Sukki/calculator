<template>
  <div class="container">
    <div class="circle">
      <div class="red-c">
        ●
      </div>
      <div class="yell-c">
        ●
      </div>
      <div class="grn-c">
        ●
      </div>
    </div>
    <div class="result">
      {{ total }}
    </div>
    <div class="keypad">
      <RuleButton rule="AC" isComplex class="AC" @click="clear"/>
      <RuleButton rule ="÷" @click="onRuleClicked"/>
    </div>
    <div class="keypad">
      <NumberButton number="7" @click="onNumberClicked"/>
      <NumberButton number="8" @click="onNumberClicked"/>
      <NumberButton number="9" @click="onNumberClicked"/>
      <RuleButton rule ="×" @click="onRuleClicked"/>
    </div>
    <div class="keypad">
      <NumberButton number="4" @click="onNumberClicked"/>
      <NumberButton number="5" @click="onNumberClicked"/>
      <NumberButton number="6" @click="onNumberClicked"/>
      <RuleButton rule ="-" @click="onRuleClicked"/>
    </div>
    <div class="keypad">
      <NumberButton number="1" @click="onNumberClicked"/>
      <NumberButton number="2" @click="onNumberClicked"/>
      <NumberButton number="3" @click="onNumberClicked"/>
      <RuleButton rule ="+" @click="onRuleClicked"/>
    </div>
    <div class="keypad">
      <NumberButton number="0" class="zero" @click="onNumberClicked"/>
      <NumberButton number="." @click="onNumberClicked"/>
      <RuleButton rule ="=" class="sum" @click="calculate"/>
    </div>
  </div>
</template>
<script>
import NumberButton from './components/NumberButton.vue'
import RuleButton from './components/RuleButton.vue'

export default {
  components: {
    NumberButton,
    RuleButton,
  },
  data () {
    return {
      total: '0',
      isClickedAdded: false,
      isOperatorAdded: false,
      isStarted: false
    }
  },
  methods: {
    onNumberClicked (clickedNumber) {
      if(this.total === '0') {
        this.total = clickedNumber;
      } else {
        this.total = this.total + clickedNumber;
      }
    },
    isOperator (clickedRule) {
      return ['+', '-', '×', '÷'].indexOf(clickedRule) > -1
    },
    onRuleClicked (clickedRule) {
      if (this.total === '0' && !this.isOperator(clickedRule)) {
        if (clickedRule === '.') {
          this.total += '' + clickedRule
          this.isClickedAdded = true
        } else {
          this.total = '' + clickedRule
        }

        this.isStarted = true
        return
      }

      if (!this.isOperator(clickedRule)) {
        if (clickedRule === '.' && this.isClickedAdded) {
          return
        }

        if (clickedRule === '.') {
          this.isClickedAdded = true
          this.isOperatorAdded = true
        } else {
          this.isOperatorAdded = false
        }

        this.total += '' + clickedRule
      }

      if (this.isOperator(clickedRule) && !this.isOperatorAdded) {
        this.total += '' + clickedRule
        this.isClickedAdded = false
        this.isOperatorAdded = true
      }
    },
    calculate () {
      const result = this.total.replace(new RegExp('×', 'g'), '*').replace(new RegExp('÷', 'g'), '/')

      this.total = parseFloat(eval(result).toFixed(9)).toString()
      this.isClickedAdded = false
      this.isOperatorAdded = false
    },
    clear () {
      this.total = '0'
      this.isClickedAdded = false
      this.isOperatorAdded = false
      this.isStarted = false
    },
  }
}
</script>

<style lang="scss" scoped>
.container{
  width:16rem;
  background-color: #3C3C3C;
  border-radius: 1rem;
  margin : 2rem;
  .circle{
    padding:0.5rem 0.7rem;
    letter-spacing:0.5rem;
    text-align:left;
    display:flex;
    .red-c{color:#FB4646;}
    .yell-c{color:#FCB024;}
    .grn-c{color:#28C131;}
  }
  .result{
    text-align:right;
    color:#ffffff;
    font-size:3rem;
    padding : 0 1rem;
    font-family: SF Pro Display,SF Pro Icons,AOS Icons,Helvetica Neue,Helvetica,Arial,sans-serif;
  }
  .keypad{
    border-radius: inherit;
    display: flex;
    .AC{
      flex: 3;
    }
    .zero{
      border-bottom-left-radius: inherit;
      flex: 2;
    }
    .sum{
      border-bottom-right-radius: inherit;
    }
  }
}
</style>
