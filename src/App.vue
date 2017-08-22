<template>
  <div id="app" class="corpo">
    <h1 class="centralizado">{{title}}</h1>
    <ul class="lista-fotos">
      <li class="lista-fotos-item" v-for="foto of fotos">
        <img :src="foto.url" :alt="foto.titulo"></img>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'AluraPic',
      fotos: []
    }
  },
  created() {
    this.$http.get('http://localhost:3000/v1/fotos')
      .then(res => res.json())
      .then(fotos => this.fotos = fotos,
      err => console.log(err));
  }
}
</script>

<style lang="scss">
  
  .corpo {
    font-family: Arial, Helvetica, sans-serif;
    width: 96%;
    margin: 0 auto;
  }

  .centralizado {
    text-align: center;
  }

  .lista-fotos {
    list-style-type: none;

  }

  .lista-fotos-item {
    display: inline-block;
  }
</style>
