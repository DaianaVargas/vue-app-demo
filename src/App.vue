<template>
  <div id="app">
    <div id="appContainer">
      <img alt="Vue logo" src="./assets/logo.png" height="80" width="80">
      <HelloWorld :msg="title"/>
      <input type="text" v-model="name"/>
      <br/>
      <br/>
      <button v-if="name != ''" @click="openNameMeaning">Significado do Nome</button>
      <br/>
      <ButtonCounter :counter="counter" :changeCounter="changeCounter"/>
      <br/>
      <br/>
      <button v-if="name != ''" @click="alertMessage">Limpar</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import ButtonCounter from './components/ButtonCounter';

export default {
  name: 'App',
  components: {
    HelloWorld,
    ButtonCounter,
  },
  data() {
    return {
      title: 'Me diga o seu nome: ',
      name: '',
      counter: 0,
    };
  },
  methods: {
    alertMessage() {
      // eslint-disable-next-line
      alert(`Adeus, ${this.name} !!!`);
      this.counter = 0;
      this.name = '';
    },
    changeCounter() {
      this.counter += 1;
    },
    openNameMeaning() {
      window.open(`//www.dicionariodenomesproprios.com.br/${this.name}/`);
    },
  },
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-image: url('https://s2.best-wallpaper.net/wallpaper/1920x1200/1205/Magic-Landscape-Sunflower-Garden_1920x1200.jpg');
  height: auto;
  left: 0;
  margin: 0;
  min-height: 100%;
  min-width: 100%;
  padding: 0;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: -1;
}
#appContainer {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
input {
  border-color: black;
  font-size: 20px;
  font-weight: bold;
  border-radius: 6px;
  padding:8px;
}
button {
  border: none;
  padding: 1rem;
  border-radius: 6px;
  cursor: pointer;
  background: #fccf08;
  color: rgb(0, 0, 0);
  font-size: 18px;
  font-weight: bold
}
</style>
