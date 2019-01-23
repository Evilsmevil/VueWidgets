<template>
    <div class = "container">
        <div class="nav-bar"> Nav Bar </div>
        <div class="left-panel">Left Panel</div>
        <div class="center-panel">Main Content</div>
        <div class="right-panel">
            Properties
            <Slider sliderName="Color" v-bind:initialValue="sliderInitialValue" v-model="sliderVal" />
            <Slider sliderName="Transparency" v-bind:initialValue="sliderInitialValue" v-model="sliderVal" />
            <Slider sliderName="Size" v-bind:initialValue="sliderInitialValue" v-model="sliderVal" />
            <Slider sliderName="Velocity" v-bind:initialValue="sliderInitialValue" v-model="sliderVal" />
            <Slider
            v-for="value in values"
            v-bind:sliderName="value.name"
            v-bind:initialValue="value.value"
            v-model="sliderVal" />

        </div>
        <div class="bottom-panel">Bottom Panel</div>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Slider from './Slider.vue';

@Component({
  components: {
    Slider,
  },
})
export default class Editor extends Vue {
@Prop() private targetObject!: object;

private values: number[] =
[
    1, 3,
];

public data() {
    return {
        values: [
            {
                value : 22,
                name: 'test1',
            },
            {
                value : 22,
                name: 'test2',
            },
        ],
    };
}

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.container {
    display : grid;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    grid-template-columns: 1fr 5fr 2fr;
    grid-template-rows: 20px 5fr 1fr
}

.nav-bar {
    text-align: center;
    grid-row: 1;
    grid-column: 1/-1; // spand the entire set of columns
}

.left-panel {
    grid-row: 2 / -1;
    grid-column: 1;
    background-color: rgb(154, 142, 221);
}

.center-panel {
    grid-row: 2;
    grid-column: 2;
    background-color: rgb(180, 29, 29);
}

.right-panel {
    grid-row: 2 / -1;
    grid-column: 3;
    background-color: rgb(49, 141, 72);
}

.bottom-panel {
    grid-row: 3;
    grid-column: 2;
    background-color: rgb(141, 139, 49);
}
</style>