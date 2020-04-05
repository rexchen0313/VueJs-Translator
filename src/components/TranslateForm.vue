<template>
    <form 
      class="translateForm"
      v-on:submit="submitForm"
    >
      <div class="submitFormHeader">
        <select v-model="language">
          <option 
            v-for="(language, index) in supportLanguagesList"
            v-bind:key="index"
            v-bind:value="language.value"
          >{{language.text}}</option>
        </select>
        <input type="submit" value="翻譯">
      </div>

        <textarea
          type="text"
          placeholder="請輸入文字 ..."
          v-model="textToTranslate"
        ></textarea>

     
    </form>

</template>

<script>
  import Support_Languages_List from '../translate_config'
  export default {
    name: 'TranslateForm',
    data() {
      return {
        supportLanguagesList: Support_Languages_List,
        textToTranslate: '',
        language: 'en'
      }
    },
    methods: {
      submitForm(e) {
        // console.log(this.supportLanguagesList[0].text);
        e.preventDefault();
        this.$emit('formSubmit', this.textToTranslate, this.language); // 向父層元件傳遞
      }
    }
  }
</script>

<style>
  .translateForm {
    background-color: blanchedalmond;
  }
  
  .submitFormHeader {
    width: 100%;
    font-size: 0;
  }
  
  .submitFormHeader select {
    width: 50%;
    height: 50px;
    text-align: center;
    font-size: 18px;
    letter-spacing: 3px;
    cursor: pointer; 
  }

  .submitFormHeader input[type="submit"] {
    background-color: #1a73e8;
    border: 0;
    color: #fff;
    width: 50%;
    height: 50px;
    font-size: 18px;
    letter-spacing: 3px;
    cursor: pointer; 
  }

  .translateForm textarea{
    background-color: #f5f5f5;
    resize: none;
    border: 0;
    width: 100%;
    height: 250px;
    padding: 8px;
    cursor: pointer; 
    font-size: 24px;
  }

  @media only screen and (min-width: 800px) {
    .translateForm {
      width: 50%;
    }

    .translateForm textarea{
      height: 500px;
    }

     .submitFormHeader select {
      height: 80px;
      font-size: 24px;
    }
    
    .submitFormHeader input[type="submit"] {
      height: 80px;
      font-size: 24px;
    }
  }
</style>
