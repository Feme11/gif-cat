<template>
  <div id="app">

    <div id="color1">
      <h2>Random Gif Cat</h2>
    </div>

    <div class="parameters" id="color2">

      <div>
        <label for="gif-titulo">Título:</label>
        <input type="text" id="gif-titulo" v-model="title"/>
      </div>

      <div>
        <label for="gif-filtro">Filtro:</label>
        <select type="text" id="gif-filtro" v-model="filter">
          <option value="blur">Blur</option>
          <option value="mono">Mono</option>
          <option value="sepia">Sepia</option>
          <option value="negative">Negative</option>
          <option value="paint">Paint</option>
          <option value="pixel">Pixel</option>
        </select>
      </div>

      <div>
        <label for="gif-color">Color:</label>
        <select type="text" id="gif-color" v-model="color">
          <option value="red">Rojo</option>
          <option value="orange">Naranja</option>
          <option value="yellow">Amarillo</option>
          <option value="green">Verde</option>
          <option value="ightskyblue">Celeste</option>
          <option value="blue">Azul</option>
          <option value="blueviolet">Violeta</option>
        </select>
      </div>
      
      <div>
        <label for="gif-tamaño">Tamaño:</label>
        <input type="text" id="gif-tamaño" v-model="size">
      </div>
      
    </div>

    <div id="color1">
      <button>Obtener mi gatito</button><br>
      <img :src="src" alt="gatito :3">
    </div>

  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      title: '',
      filter: '',
      color: '',
      size: '',
    }
  },
  computed: {
    src(){
      let title = this.title;
      let filter = this.filter;
      let color = this.color;
      let size = this.size;
      return `https://cataas.com/cat/gif/says/${title}?filter=${filter}&color=${color}&size=${size}`
    }
  }
}
</script>

<style>
*{
  margin: 0;
}
.parameters{
  display: flex;
  flex-direction: column;
}

#color1{
  background-color: #f08080;
}

#color2{
  background-color: #add8e6;
}

</style>
