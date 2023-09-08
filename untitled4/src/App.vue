<template>
  <div id="window">
    <div id="main">
      <div class="slider">
        <a v-on:click="cats" class="slider-bottom" :class="{ active: catsColor }">Котики</a> <!--Слушаю клики, обращаюсь к соответствующим методам-->
        <a v-on:click="dogs" class="slider-bottom" :class="{ active: dogsColor }">Собаки</a>
        <a v-on:click="crocodiles" class="slider-bottom" :class="{ active: crocodilesColor }">Крокодилы</a>
        <a v-on:click="capibaras" class="slider-bottom" :class="{ active: capibarasColor }">Капибары</a>
        <a v-on:click="broccoli" class="slider-bottom" :class="{ active: broccoliColor }">Брокколи</a>
      </div>
      <div id="title">
        <h1>Вы видите {{ text }}</h1>
      </div>
      <div class="image">
        <component :is="img"></component>
      </div>
    </div>
  </div>
</template>

<script>
import {createApp} from "vue"; //Создаю экземпляр приложения
import imgOne from "@/components/imgOne"; //Импортирую компоненты
import imgTwo from "@/components/imgTwo";
import imgThree from "@/components/imgThree";
import imgFour from "@/components/imgFour";
import imgFive from "@/components/imgFive";
export default {
  name: 'App',
  data() {
    return {
      text: 'котиков', //Переменные, которые буду менять в методах
      img: imgOne,
      catsColor: false,
      dogsColor: false,
      crocodilesColor: false,
      capibarasColor: false,
      broccoliColor: false
    };
  },
  methods: {
    cats() {
      this.text = 'котиков'
      this.img = imgOne
      this.catsColor = true
      this.dogsColor = false
      this.crocodilesColor= false
      this.capibarasColor = false
      this.broccoliColor = false
    },
    dogs() {
      this.text = 'собачек'
      this.img = imgTwo
      this.catsColor = false
      this.dogsColor = true
      this.crocodilesColor= false
      this.capibarasColor = false
      this.broccoliColor = false
    },
    crocodiles() {
      this.text = 'крокодилов'
      this.img = imgThree
      this.catsColor = false
      this.dogsColor = false
      this.crocodilesColor= true
      this.capibarasColor = false
      this.broccoliColor = false
    },
    capibaras() {
      this.text = 'капибар'
      this.img = imgFour
      this.catsColor = false
      this.dogsColor = false
      this.crocodilesColor= false
      this.capibarasColor =true
      this.broccoliColor = false
    },
    broccoli() {
      this.text = 'брокколи'
      this.img = imgFive
      this.catsColor = false
      this.dogsColor = false
      this.crocodilesColor= false
      this.capibarasColor = false
      this.broccoliColor = true
    },
  }, components: {
    imgOne,
    imgTwo,
    imgThree,
    imgFour,
    imgFive
  }
};
createApp({}).mount('#window') //Монтирую приложение
</script>

<style>
h1 {
  margin: 0;
}
.image {
  margin-top: 50px;
  width: 500px;
  height: 300px;
}
#window {
  width: 100%;
  height: 700px;
  background-color: #42b983;
  display: flex;
  align-items: center;
}
#main {
  width: 500px;
  height: auto;
  margin-left: auto;
  margin-right: auto;
  background-color: white;
  border-radius: 10px;
}
.slider {
  width: 100%;
  height: 60px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.slider-bottom {
  width: 100%;
  height: 20px;
  text-align: center;
  cursor: pointer;
  border-bottom: solid 2px darkgray;
}
.slider-bottom:hover {
  background-image: radial-gradient(farthest-side at bottom, cadetblue -90%, #fff);
}
#title {
  width: 100%;
  height: 20px;
  text-align: center;
}
.active {
  color: #42b983;
  border-bottom: solid 2px #42b983;
}
</style>
