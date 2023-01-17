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
      0
    </div>
    <div class="keypad">
      <RuleButton rule="AC" isComplex />
      <RuleButton rule="+/-" isComplex />
      <RuleButton rule="%" isComplex />
      <RuleButton rule ="÷"/>
    </div>
    <div class="keypad">
      <NumberButton number="7"/>
      <NumberButton number="8"/>
      <NumberButton number="9"/>
      <RuleButton rule ="×"/>
    </div>
    <div class="keypad">
      <NumberButton number="4"/>
      <NumberButton number="5"/>
      <NumberButton number="6"/>
      <RuleButton rule ="-"/>
    </div>
    <div class="keypad">
      <NumberButton number="1"/>
      <NumberButton number="2"/>
      <NumberButton number="3"/>
      <RuleButton rule ="+"/>
    </div>
    <div class="keypad">
      <NumberButton number="0" class="zero"/>
      <NumberButton number="."/>
      <RuleButton rule ="=" class="sum"/>
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
