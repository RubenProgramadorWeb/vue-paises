<script setup>
import { ref } from 'vue';

const urlApi = 'https://restcountries.com/v3.1/region/europe';

function recuperaCountries() {
  fetch(urlApi)
    .then((respuesta) => respuesta.json())
    .then((data) => {

      console.log(data)
      countries.value = data;
    })
}

recuperaCountries();


const countries = ref([]);

// nombre.value = 'Luis';
</script>

<template>
  App limpia
  <br>
  {{ urlApi }}
  <br><br>
  <h2>Mostramos uno solo</h2>
  <br>
  {{ countries[0].name.official }}
  <br> <br>
  <h2>Usamos un bucle for para mostrar todo el array. Usaremos un div pero podemos usar otras etiquetas.</h2>
  <br>
  <div v-for="country in countries">{{ country.name.official }}</div>
</template>
