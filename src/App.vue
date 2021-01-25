<template>
  <div class="container">
    <div class="badge bg-secondary">
      <!-- La barra vertical indica que se va a aplicar un filtro a todo lo que esté antes de ella, en este caso a mensaje -->
      <span>{{ mensaje | mayuscula }}</span>
      <hr>
      <!-- Uso de un filtro global -->
      <span>{{ mensaje | suspensivos }}</span>
      <hr>
      <!-- Uso de más de un filtro, recordar que los filtros usan todo lo que tengan a la izquierda -->
      <span>{{ mensaje | suspensivos | mayuscula }}</span>
      <hr>
      <span>Mensaje sin filtro: {{ mensaje }}</span>
      <hr>
      <span>Temperatura: {{ temperatura | aFahrenheit }}</span>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      mensaje: 'Hola mundo desde Vue',
      temperatura: 20
    }
  },
  // Definimos nuestros filtros
  filters: {
    mayuscula(mensajeParaConvertir) {
      return mensajeParaConvertir.toUpperCase()
    },
    aFahrenheit(temperatura) {
      return ((9/5)*temperatura)+32+'F'
    }
  }
}
</script>

<style>

</style>
