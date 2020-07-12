<template>
  <div id="app">
    <Cabecera></Cabecera>
    <Lista></Lista>
  </div>
</template>

<script>
import Cabecera from './components/Cabecera'
import Lista from './components/Lista'

export default {
  name: 'App',
  components: {
    Cabecera,
    Lista
  }
}
</script>