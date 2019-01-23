<template>
  <div id="app">
    <Editor class="myTable"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Slider from './components/Slider.vue';
import Editor from './components/Editor.vue';

@Component({
  components: {
    Slider,
    Editor,
  },
})

export default class App extends Vue {
  private sliderInitialValue: number = 13;
  private sliderVal: number = this.sliderInitialValue;

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
  height: 100%;
}

</style>
