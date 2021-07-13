<template lang="html">

  <section class="codificador">
    <input v-model="message" placeholder="Escriba un texto">
    <br/>
    <div v-if='this.cantidadLetras>0'>
      <p>Cantidad de letras: {{this.cantidadLetras}}</p>
      <br/>
      <p>Vocales cambiadas: {{this.cambiarVocales()}}</p>
      <br/>
      <p>Texto en mayúscula: {{this.cambiarMayusculas()}}</p>
      <br/>
      <p>Texto en mínuscula: {{this.cambiarMinusculas()}}</p>
      <br/>
      <p>Mayúscula intercalada: {{this.mayusculaIntercalada()}}</p>
      <br/>
      <p>Minúscula intercalada: {{this.minusculaIntercalada()}}</p>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'codificador',
    props: [],
    mounted () {

    },
    data () {
      return {
        message:''

      }
    },
    methods: {
      cambiarVocales(){
        let array = this.message.toLowerCase().split('');
        for (let index = 0; index < array.length; index++) {
          switch (array[index]) {
            case 'a':
              array[index] = 'u';
              break;
            case 'e':
              array[index] = 'o';
              break;
            case 'o':
              array[index] = 'e';
              break;
            case 'u':
              array[index] = 'a';
              break;
            default:
              break;
          }
        }
        let palabra = array.join('');
        return palabra;
      },
      cambiarMayusculas(){
        return this.message.toUpperCase();
      },
      cambiarMinusculas(){
        return this.message.toLowerCase();
      },
      mayusculaIntercalada(){
        let array = this.message.toLowerCase().split('');
        for (let index = 0; index < array.length; index++) {
          if(index%2==0){
            array[index] = array[index].toUpperCase();
          }
        }
        let palabra = array.join('');
        return palabra;
      },
      minusculaIntercalada(){
        let array = this.message.toLowerCase().split('');
        for (let index = 0; index < array.length; index++) {
          if(index%2!=0){
            array[index] = array[index].toUpperCase();
          }
        }
        let palabra = array.join('');
        return palabra;
      }
    },
    computed: {
      cantidadLetras: function(){
        let array = this.message.split('');
        return array.length;
      }
    }

}


</script>

<style scoped lang="css">
  .codificador {

  }
</style>
