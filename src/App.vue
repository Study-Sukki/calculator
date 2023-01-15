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
    <div class="result"> // TODO: Input으로 바꾸기
      0
    </div>
    <div class="keypad">
      <button class="etc">
        AC
      </button>
      <button class="etc">
        +/-
      </button>
      <button class="etc">
        %
      </button>
      <button class="rule">
        ÷
      </button>
    </div>
    <div class="keypad">
      <button class="number">
        7
      </button>
      <button class="number">
        8
      </button>
      <button class="number">
        9
      </button>
      <button class="rule">
        ×
      </button>
    </div>
    <div class="keypad">
      <button class="number">
        4
      </button>
      <button class="number">
        5
      </button>
      <button class="number">
        6
      </button>
      <button class="rule">
        -
      </button>
    </div>
    <div class="keypad">
      <button class="number">
        1
      </button>
      <button class="number">
        2
      </button>
      <button class="number">
        3
      </button>
      <button class="rule">
        +
      </button>
    </div>
    <div class="keypad">
      <button class="number zero">
        0
      </button>
      <button class="number">
        .
      </button>
      <button class="rule sum">
        =
      </button>
    </div>
  </div>
</template>

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
    display: flex;

    > button {
      flex: 1;
      border:0.3px solid #3C3C3C;
      width:4rem;
      font-size: 1.2rem;
      padding:0.6rem 0;
      text-align:center;
    }
    .etc{
      background-color:#4E4E4E;
      color:#D9D9D9;
    }
    .rule {
      color:#FFEEDC;
      background-color:#FD8E0E;
    }
    .zero{
      flex: 2;
      border-bottom-left-radius:1rem;
    }
    .sum{
      border-bottom-right-radius:1rem;
    }
  }
}
</style>
