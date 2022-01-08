<template>
  <div>
    <h1>{{ msg }}</h1>
    <Subtitulo  msg="Bienvenido a su cuenta"/>
  </div>
</template>

<script>

import Subtitulo from './Subtitulo'
export default {
  name: 'Titulo',
  props: {
    msg: String
  },
  components: {
    Subtitulo
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
