<template>
  <h2>{{translatedText}}</h2>
</template>

<script>
export default {
  name: 'translateOutput',
  props: ['translatedText']

}
</script>

<style>
h2{
  margin-top: 10vh;
  background-color: white;
  font-family: 'Scheherazade','Tahoma', serif;
  font-size: 50px;
  border: 3px solid black;
  display: inline-flex;
  }
</style>
