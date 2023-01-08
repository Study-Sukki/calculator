<template>
  <div class="container">
    <div class="login-msg">
      네이버를 더 안전하고 편리하게 이용하세요
    </div>
    <button class="naver-login">
      NAVER 로그인
    </button>
    <div class="sub-area">
      <div class="left">
        <button class="button">
          아이디
        </button>
        <button class="button">
          비밀번호
        </button>
      </div>
      <button class="button">
        회원가입
      </button>
    </div>
    

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #f7f9fa;
  border: 1px solid #dae1e6;
  padding: 1.2rem;

}
.login-msg{
  color: gray;
  padding-left: 3px;
  text-align: left;
}
.naver-login{
  padding: 1.5rem 0;
  width: 100%;
  margin-top: 11px;
  background-color: #19ce60;
  border:1px solid #15c654;
  font-size:13px;
  color: #fff;
  font-weight: 700;
  text-align: center;
}
.sub-area{
  height: 3rem;
  display: flex;
  justify-content: space-between;
  .left {
    display: flex;
  }
  .button {
    color:#404040;
    letter-spacing: -.2px;
    border: none;
    background-color: transparent;
  }
}

</style>
