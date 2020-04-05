<template>
  <div class="translateOutput">
    <h3>翻譯結果:</h3>
    <div class="resultText">
      <span><slot></slot></span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'TranslateOutput',
  }
</script>

<style>
  .translateOutput {
    background-color: #fff;
  }
  .translateOutput h3 {
    background-color: #1e2930;
    color: #fff;
    letter-spacing: 3px;
    font-size: 24px;
    height: 50px;
    line-height: 50px;
  }
  .translateOutput .resultText {
    background-color: #f5f5f5;
    text-align: left;
    width: 100%;
    height: 250px;
    padding: 8px;
    font-size: 24px;
  }
  @media only screen and (min-width: 800px) {
    .translateOutput{
      width: 50%;
      border-left: 1px solid #7a7a7a;
    }
    .translateOutput .resultText {
      background-color: #f5f5f5;
      text-align: left;
      width: 100%;
      height: 500px;
      padding: 8px;
    }
    .translateOutput h3 {
      font-size: 24px;
      height: 80px;
      line-height: 80px;
    }
  }
</style>
