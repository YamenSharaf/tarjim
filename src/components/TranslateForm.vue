<template>
  <div class="row" id="translateForm">
    <div class="col-sm-offset-2 col-sm-8 col-md-offset-3 col-md-6" id="transform">
    <form v-on:submit="formSubmit" id="form-style">
      <input class="form-control" type="text" v-model="textToTranslate" placeholder="أدخــل النــص هنــا">
      <br>
      <input class="btn btn-primary" type="submit" value="تـــــرجــم">
    </form>
    </div>
    </div>
</template>

<script>
export default {
  name: 'translateForm',
  data() {
    return {
      textToTranslate: ''
    }
  },
  methods: {
    formSubmit(e) {
      this.$emit('formSubmit', this.textToTranslate)
      e.preventDefault();
      var form = document.getElementById("form-style");
      form.reset();
    }
  }

}
</script>

<style>
#transform {
  background-color: white;
  border: 3px black solid;
  padding: 20px;

}
input{
   text-align:center;
   font-family: 'Scheherazade', serif;
   font-size: 50px;
   font-weight: bold;
   margin: -5px;
   border-radius: 0px;
}
.form-control {
  border-radius: 0px;
}
.btn{
  font-weight: bold;
  width: 100px;
  font-size: 20px;
}
.row{

}

</style>
