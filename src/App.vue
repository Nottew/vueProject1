<template>
  <div>
   <header>
            <nav>
                <a href="#" @click="switchView('square')">Квадрат</a>
                <a href="#" @click="switchView('triangle')">Треугольник</a>
                <a href="#" @click="switchView('circle')">Круг</a>
                <a href="#" @click="switchView('egg')">Яйцо</a>
            </nav>
   </header>
   <square v-if="currentView == 'square'"/>
   <circle v-else-if="currentView == 'circle'"/>
   <triangle v-else-if="currentView == 'triangle'"/>
   <egg v-else/> 
  </div>
</template>

<script>
import square from './components/f1';
import circle from './components/f2';
import triangle from './components/f3';
import egg from './components/f4';

export default {
  name: 'App',
  data() {
    return {
      currentView: ''
    }
  },
  components: {
    square,
    circle,
    triangle,
    egg
  },
  methods: {
    switchView: function (arg) {
      this.currentView = arg;
    }
  }
}
</script>

<style>
* {
    box-sizing: border-box;
}

body {
    padding: 0;
    margin: 0;
    font-family: 'Roboto', sans-serif;
}

header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 48px;
}

nav {
    list-style:none;
    margin:0;
    padding:0;
    text-align:center;
}

nav a {
    display: inline-block;
    padding: 16px 20px;
    text-decoration: none;
    color:  #8a8d96;
    font-weight: 400;
}

nav a:hover {
    color: #272727;
}

/* Фигуры */
.square,
.triangle,
.circle,
.egg {
    position: absolute;
    top: 120px;
    left: 50%;
}

.square {
    width: 240px;
    height: 240px;
    background-color: #00bcd4;
    margin-left: -120px;
}

.triangle {
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 0 120px 207.8px 120px;
    border-color: transparent transparent #3f51b5 transparent;
    margin-left: -120px;
}

.circle {
    width: 240px;
    height: 240px;
    border-radius: 50%;
    background-color: #cddc39;
    margin-left: -120px;
}

.egg {
    width: 168px;
    height: 240px;
    background-color: #ffc107;
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    margin-left: -84px;
}

.switch-enter-active,  .switch-leave-active {
    transition: all 0.6s ease-in-out;
}

.switch-enter {
    left: -50%;
}
.switch-leave-to {
    left: 150%;
}

.switch-enter-to {
    left: 50%
}
.switch-leave {
    left: 50%
}
</style>