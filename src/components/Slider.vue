<template>
    <div class = "slidercontainer">
        <span class = "sliderName"> {{sliderName}} </span>
        <input v-model="value" v-on:input="$emit('input', $event.target.value)" type="range" min="1" max="100" class="slider">
        <span class = "valueLabel"> {{value}} </span>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Slider extends Vue {

@Prop() private initialValue! : number;
@Prop() private sliderName! : string;

private value : number = 0;

private onClick(params: Event) : void {
      console.log("Hi!" + params.timeStamp);
  }

  data () {
      return {
          value : this.initialValue
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.slidercontainer {
  width: 100%; /* Width of the outside container */
}

.slider {
  -webkit-appearance: none;
  width: 80%;
  height: 15px;
  border-radius: 5px;  
  background: #d3d3d3;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.valueLabel {
    width:  10%;
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