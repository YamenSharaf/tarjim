<template>
  <div id="app" class="text-center">
    <h1 class="text-primary">ترجم</h1>
    <h3>ترجم من أي لغة إلى العربية</h3>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'app',
  components:{
    TranslateForm,
    TranslateOutput
  },
  data: function() {
    return {
      translatedText:''
    }
  },
  methods: {
    translateText: function(text) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170410T063226Z.2ac369d2fa38150a.89201083f38398d1e833ed54603c34f7f62d01f1&lang=ar&format=plain&text='+text)
      .then((response) => {
        this.translatedText = response.body.text[0];
      } )
    }
  }
}
</script>

<style>
body{
  background-image: url('http://i.imgur.com/HPe4d3q.jpg');
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: 50% 100%;
  background-size: cover;
  height: 100vh;
}
h3 {
  font-size: 50px;
  font-family: 'Scheherazade', 'Tahoma' , serif;
}

h1{
  margin-top: 10vh;
  font-size: 120px;
  font-family: 'Aref Ruqaa','Tahoma', serif;
  margin-bottom: 15vh;
}
</style>
