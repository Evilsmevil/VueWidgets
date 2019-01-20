<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Slider</h1>
    <div style="width:25%; display:block; margin-left:auto; margin-right:auto;">
      <Slider sliderName="Opacity" v-bind:initialValue="sliderInitialValue" v-model="sliderVal" />
    </div>
    <h1> {{sliderVal}} </h1>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Slider from './components/Slider.vue';

@Component({
  components: {
    Slider,
  },
})

export default class App extends Vue {
  private sliderInitialValue : number = 13;
  private sliderVal : number = this.sliderInitialValue;

}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
