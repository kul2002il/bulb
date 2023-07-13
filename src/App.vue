<script setup>
import Rules from './components/Rules.vue'
import Bulb from './components/Bulb.vue'
</script>

<script>
let data = {
    bulbs: [
        {
            balls: [
                {color: "blue"},
                {color: "blue"},
                {color: "blue"},
            ],
        },
        {
            balls: [
                {color: "blue"},
                {color: "blue"},
                {color: "blue"},
            ],
        },
        {
            balls: [
                {color: "blue"},
                {color: "blue"},
                {color: "blue"},
            ],
        },
    ],
};

export default {
    data() {return data},
}

</script>

<template>
    <h1>Пробирки</h1>
    <Rules/>
    <br>
    <Bulb
        v-for="bulb in bulbs"
        :data="bulb"
    />
</template>

<style>
</style>
