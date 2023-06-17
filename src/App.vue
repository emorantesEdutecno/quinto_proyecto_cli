<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!--
      <HelloWorld msg="Welcome to Your Vue.js App"/>
    -->
    <SesionDosComponent />
    <hr>
    <SesionTresComponent 
      v-bind:juegos="arregloJuegos"
      v-on:juegoAEliminar = "eliminarDelArregloJuegos"
      v-on:juegoAInsertar = "insertarJuegoEnElArreglo"
    />
    <hr>
    <SesionCuatroComponent 
      v-bind:imagenes="arregloImagenes"
      v-bind:descripciones="arregloDescripciones"
      v-bind:autores="arregloAutores"
    />

  </div>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import SesionDosComponent from '@/components/SesionDosComponent.vue';
import SesionTresComponent from '@/components/SesionTresComponent.vue';
import SesionCuatroComponent from '@/components/SesionCuatroComponent.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    SesionDosComponent,
    SesionTresComponent,
    SesionCuatroComponent,
  },
  data:function(){
    return{
      arregloJuegos:['Arena of Valor', 'Pokemon Unite', 'Donkey Kong', 'Heroes of the Storm', 'Valorant'],
      arregloImagenes:[
        'https://i.blogs.es/7e1268/one-piece/1366_2000.jpeg',
        'https://i0.wp.com/codigoespagueti.com/wp-content/uploads/2021/11/Usopp-One-Piece-cosplay-femenino.jpg',
        'https://i.blogs.es/e4c931/chopper-en-one-piece/840_560.jpeg'
      ],
      arregloDescripciones:[
        'El capitan Monkey D.Luffy',
        'El gran tirador Ussop',
        'El tierno Chopper'
      ],
      arregloAutores:[
        'Eichiro Oda',
        'Eichiro Oda',
        'Eichiro Oda',
      ],
    }
  },
  methods:{
    eliminarDelArregloJuegos:function(indiceJuego){
      this.arregloJuegos.splice(indiceJuego,1);
    },
    insertarJuegoEnElArreglo: function(nombreJuego){
      this.arregloJuegos.push(nombreJuego);
    },
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
