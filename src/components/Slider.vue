<template>
    <div class = "slidercontainer">
        <span class = "valueName"> {{sliderName}} </span>
        <input v-model="value" v-on:input="$emit('input', $event.target.value)" type="range" min="1" max="100" class="slider">
        <span class = "valueDigits"> {{value}} </span>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Slider extends Vue {

@Prop() private initialValue!: number;
@Prop() private sliderName!: string;
private value: number = 0;

public data() {
    return {
        value: this.initialValue,
    };
  }


// private onClick(params: Event) : void {
//   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss"  scoped>
.slidercontainer {
  width: 100%; /* Width of the outside container */
  display:flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.slider {
  -webkit-appearance: none;
  flex-grow: 1;
  height: 15px;
  border-radius: 5px;  
  background: #d3d3d3;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.valueName {
    flex-grow: 0;
    min-width: 100px;
    align-items: flex-start;
    text-align: left;
}

.valueDigits {
    min-width: 2em;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%; 
  background: $fg-primary;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: $fg-primary;
  cursor: pointer;
}

/* Mouse-over effects */
.slider:hover {
  opacity: 1; /* Fully shown on mouse-over */
}
</style>