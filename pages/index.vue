<template>
  <div class="main">
    <div class="page-title">
      <div class="page-main-title">
        <span>クイズ自動生成</span>
      </div>
      <div class="page-sub-title">
        <span>入力された単語をもとにクイズを生成してくれるサイトです。</span>
      </div>
    </div>
    <div class="word-field">
      <input placeholder="生成ワード">
    </div>
    <div class="generate-button">
      <span>生成</span>
    </div>
  </div>
</template>

<script>
import axios from "axios";

axios.defaults.headers.post['Content-Type'] = 'application/json;charset=utf-8';
axios.defaults.headers.post['Access-Control-Allow-Origin'] = '*';

export default {
  data() {
    return {

    }
  },
  asyncData ({}) {
    console.log("Generate")

    let data = axios.get("https://quiz-generator-api.herokuapp.com/generate/", {
      params: {
        "word": "日清戦争"
      }
    })
    .then((response) => {
        console.log(response)
      })
    }
}
</script>

<style scoped>
@media (min-width: 600px) {
  div.main {
    width: 100vw;
    position: relative;
  }
  div.page-title {
    height: 12vw;
    width: 80vw;
    position: absolute;
    top: 8vw;
    left: 0;
    right: 0;
    margin: auto;
  }
  div.page-title div.page-main-title {
    height: 8vw;
    width: 80vw;
    text-align: center;
  }
  div.page-title div.page-main-title span {
    font-size: 4vw;
    line-height: 8vw;
    font-weight: bold;
    font-family:"Yu Gothic", "游ゴシック", YuGothic, "游ゴシック体", "ヒラギノ角ゴ Pro W3", "メイリオ", sans-serif;
  }
  div.page-title div.page-sub-title {
    height: 4vw;
    width: 80vw;
    position: absolute;
    bottom: 0;
    text-align: center;
  }
  div.page-title div.page-sub-title span {
    font-size: 2.4vw;
    line-height: 4vw;
    font-weight: bold;
    font-family:"Yu Gothic", "游ゴシック", YuGothic, "游ゴシック体", "ヒラギノ角ゴ Pro W3", "メイリオ", sans-serif;
  }
  div.word-field {
    height: 4vw;
    width: 40vw;
    position: absolute;
    left: 0;
    right: 0;
    top: 25vw;
    margin: auto;
    border-radius: 2vw;
    border: solid 0.2vw black;
  }
  div.word-field input {
    width: 30vw;
    height: 3.6vw;
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    font-size: 2vw;
    border-radius: 2vw;
    border: none;
    outline: none;
  }
  div.generate-button {
    height: 4vw;
    width: 20vw;
    position: absolute;
    left: 0;
    right: 0;
    top: 40vw;
    margin: auto;
    border-radius: 2vw;
    border: solid 0.2vw black;
    text-align: center;
  }
  div.generate-button:hover {
    background-color: rgb(10, 10, 10, 0.2);
  }
  div.generate-button span {
    font-size: 2vw;
    line-height: 4vw;
    font-weight: bold;
    font-family:"Yu Gothic", "游ゴシック", YuGothic, "游ゴシック体", "ヒラギノ角ゴ Pro W3", "メイリオ", sans-serif;
  }
}
</style>