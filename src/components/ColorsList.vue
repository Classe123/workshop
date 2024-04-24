<template>
    <section class="container">
        <div class="d-flex justify-content-between align-items-center  my-4">
            <h2>Colors</h2>
            <SearchBar @searchpalette="setPalette($event)" />
        </div>

        <div class="d-flex justify-content-center align-items-center">

            <div class="circle" v-for="(color, index) in filteredColors" :key="color.hex"
                :style="{ 'background-color': color.hex }" @click="activeIndex = index"></div>
        </div>
        <div class="box p-4 text-white" :style="{ 'background-color': filteredColors[activeIndex].hex }">
            <h5>{{ filteredColors[activeIndex].label }}</h5>
            <div>hex: {{ filteredColors[activeIndex].hex }}</div>
            <div>Palette: {{ filteredColors[activeIndex].palette_name }}</div>
        </div>
    </section>
</template>

<script>
import { store } from '../store.js';
import SearchBar from './SearchBar.vue';
export default {
    name: 'ColorsList',
    components: {
        SearchBar
    },
    data() {
        return {
            store,
            activeIndex: 0,
            palette: ''
        }
    },
    methods: {
        setPalette(event) {
            console.log(event);
            this.palette = event;
        }
    },
    computed: {
        filteredColors() {
            return this.store.colors.filter(color => color.palette_name === this.palette || this.palette === '');
        }
    }
}
</script>

<style lang="scss" scoped>
.circle {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin: 0 10px;
    border: 1px solid black;
}

.box {
    width: 400px;
    height: 200px;
    border: 1px solid black;
    margin: 50px auto;
}
</style>