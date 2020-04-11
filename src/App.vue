<template>
  <div id="app">
    <header>
      <h1>翻譯軟體</h1>
    </header>
    <div id="container">
      <TranslateForm v-on:formSubmit="textTraslate"></TranslateForm>
      <TranslateOutput>{{translateText}}</TranslateOutput>
    </div>
  </div>
</template>

<script>
  import TranslateForm from './components/TranslateForm'
  import TranslateOutput from './components/TranslateOutput'

  export default {
    name: 'App',
    data() {
      return {
        translateText: '',
        lastTimeTranslateText: ''
      }
    },
    components: {
      TranslateForm,
      TranslateOutput
    },
    methods: {
      textTraslate(text, language) {
        if (text.length > 0 && text != this.lastTimeTranslateText) { 
          const KEY = process.env.VUE_APP_APIKEY;
          const API = `https://translate.yandex.net/api/v1.5/tr.json/translate?key=${KEY}&text=${text}&lang=${language}`;
          this.$http.get(API).then((res) => {
            console.log(res.body.text);
            this.translateText = res.body.text[0];
          });
          this.lastTimeTranslateText = text;
        }
      }
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    background-color: #000;
    color: #2c3e50;
    width: 100%;
  }

  header {
    background-color: #42b983;
  }

  header h1 {
    font-size: 36px;
    letter-spacing: 3px;
    height: 80px;
    line-height: 80px;
  }

  #container {
    display: flex;
    flex-direction: column;
  }

  @media only screen and (min-width: 800px) {
    #app {
      max-width: 1000px;
      margin: 0 auto;
    }
    
    #container {
      flex-direction: row;
    }
  }
</style>
