<template>
  <div id="app">
    <h1>ini state {{number}} {{alamat}}</h1>
    <HelloWorld msg="tentang alamat"/>
    <p>{{getName}} itu name</p>
    <p>{{people.age}} itu age</p>
    <p>{{people.address}} itu address</p>
    <p>{{numberIcr}}</p>
    <button v-on:click="changeName">Ganti nama menjadi bubu</button>
    <button @click="displayAlert">Display</button>
    <p v-for="h in cars" v-bind:key="h">{{h}}</p>

    <img v-if="image" alt="Vue logo" src="./assets/logo.png">
    <img v-else alt="gambar 2" src="./assets/a.png">

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: ()=> {
    return {
      number: 1,
      alamat: 'jl. kaliurang no. 20',
      people: {
        name: 'Aisyah',
        age: 20,
        address: 'Yogja'
      },
      cars: ['CRV', 'JAZZ', 'MOBILIO'],
      image: true
    }
  },
  computed: {
    getName(){
      return this.people.name.toUpperCase();
    },
    numberIcr(){
      return  'selamat datang';
    }
  },
  methods: {
    changeName(){
      this.people.name = 'Bubu';
    },
    displayAlert(){
      alert(this.number);
    }
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
