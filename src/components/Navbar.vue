<template>
  <div class="fill" style="background-color: grey;">
      <nav class="nav" style="background-color: grey;">
            <div class="nav-center">
                <div class="nav-item">
                  <button class="button" style="background-color: black; color: white" v-bind:class="{ 'is-active': 1 == selected }" @click="select(1)">Adicionar Vertice</button>
                  <button class="button" style="background-color: black; color: white" v-bind:class="{ 'is-active': 2 == selected }" @click="select(2)">Adicionar Aresta</button>
                  <button class="button" style="background-color: black; color: white" v-bind:class="{ 'is-active': 3 == selected }" @click="select(3)">Mover</button>
                  <button class="button is-danger is-outlined" v-bind:class="{ 'is-active': 4 == selected }" @click="select(4)">Remover</button>
                  <button class="button" style="background-color: black; color: white" v-bind:class="{ 'is-active': 5 == selected }" @click="select(5)">Welsh e Powell</button>
                  <button class="button" style="background-color: black; color: white" v-bind:class="{ 'is-active': 6 == selected }" @click="select(6)">DSATUR</button>
                  <button class="button" style="background-color: black; color: white"  v-bind:class="{ 'is-active': 7 == selected }" @click="select(7)">Prim</button>
                  <button class="button" style="background-color: orange; color: white" v-bind:class="{ 'is-active': 8 == selected }" @click="select(8)">Limpar</button>
                </div>

            </div>

        </nav>
        <p style="text-align: center">{{msg}}</p>
        <board :btnSelected="selected"></board>
        </div>
</template>

<script>

import Board from './Board';

export default {
  name: 'navbar',
  data () {
    return {
      selected: '',
      msg: ''
    }
  },
  methods: {
    select(number){
      let self = this;
      self.selected = number;
      switch(number){
        case 1:
          self.msg = "Clique na tela para adicionar vertices!";
          break;
        case 2:
          self.msg = "Clique no vertice inicial e depois clique novamente no final para adicionar a aresta!";
          break;
        case 3:
          self.msg = "Clique no vertice e segure para mover!";
          break;
        case 4:
          self.msg = "Clique no vertice para remover!";
          break;
        case 5:
          self.msg = "Clique no espaço em branco para executar o algoritmo Wesh e Powell!";
          break;
        case 6:
          self.msg = "Clique no espaço em branco para executar o algoritmo DSATUR!";
          break;
        case 7:
          self.msg = "Clique no espaço em branco para executar o algoritmo PRIM!";
          break;
        case 8:
          location.reload();
          break;
      }
    }
  },
  components: {
    Board
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .fill{
    height: 100%;
  }
</style>
