<template>

  <section class="src-components-formulario">

    <input type="text" id="input" placeholder="Ingrese un texto aqui" v-model.trim="textoInput">
    <br>
    <br>

    <p v-if="textoInput">Cantidad de Caracteres: {{ cantidadDeCaracteres }}</p>
    <p v-if="textoInput">Cantidad de Vocales: {{ cantidadDeVocales }}</p>
    <p v-if="textoInput">Texto en Mayuscula: {{ mayuscula }}</p>
    <p v-if="textoInput">Texto Invertido: {{ textoInvertido }}</p>

    <hr>

    <p>Respuestas 1: C - 2:C - 3: A</p>
  </section>

</template>

<script lang="js">

export default {
  name: 'src-components-formulario',
  props: [],
  mounted() {

  },
  data() {
    return {
      textoInput: null
    }
  },
  computed: {

    cantidadDeCaracteres() {
      return this.textoInput ? this.textoInput.length : 0;
    },

    cantidadDeVocales() {
      const cadenaMinuscula = this.textoInput.toLowerCase();
      const vocales = "aeiou";
      let contador = 0;

      for (let char of cadenaMinuscula) {
        if (vocales.includes(char)) {
          contador++;
        }
      }
      return contador;
    },

    cantidadDeVocales() {
      const cadenaMinuscula = this.textoInput.toLowerCase();
      const vocales = "aeiou";
      let contador = 0;

      for (let char of cadenaMinuscula) {
        if (vocales.includes(char)) {
          contador++;
        }
      }
      return contador;
    },

    mayuscula(){
      return this.textoInput.toUpperCase()
    },

    textoInvertido() {
      return this.textoInput.split("").reverse().join("");
    }



  }
}

</script>

<style scoped lang="css">
p {
  font-size: 17px;
  font-weight: 500;
}
</style>