<script setup>
import Rules from './components/Rules.vue'
import Bulb from './components/Bulb.vue'
</script>

<script>

let data = {
    state: {
        select: null
    },
    bulbs: [
        {
            capacity: 4,
            balls: [
                {color: "blue"},
                {color: "red"},
                {color: "blue"},
                {color: "blue"},
            ],
        },
        {
            capacity: 4,
            balls: [
                {color: "red"},
                {color: "blue"},
                {color: "blue"},
                {color: "blue"},
            ],
        },
        {
            capacity: 4,
            balls: [
                {color: "blue"},
                {color: "blue"},
                {color: "red"},
                {color: "red"},
            ],
        },
        {
            capacity: 4,
            balls: [],
        },
    ],
};

export default {
    data() {return data},
    methods: {
        click(bulb_key) {
            if (this.state.select === null) {
                if (this.bulbs[bulb_key].balls.length > 0) {
                    this.state.select = bulb_key;
                }
                return;
            }
            if (this.state.select === bulb_key) {
                this.state.select = null;
                return;
            }
            if (
                this.bulbs[bulb_key].balls.length === 0
                || this.bulbs[bulb_key].balls[0].color === this.bulbs[this.state.select].balls[0].color
            ){
                if (this.bulbs[bulb_key].balls.length >= this.bulbs[bulb_key].capacity) {
                    return;
                }
                this.bulbs[bulb_key].balls.unshift(
                    this.bulbs[this.state.select].balls.shift()
                );
                this.state.select = null;
            }
        }
    },
}

</script>

<template>
    <h1>Пробирки</h1>
    <Rules/>
    <div class="shelf">
        <Bulb
            v-for="(bulb, key) in bulbs"
            :data="bulb"
            :selected="state.select===key"
            @click="click(key)"
        />
    </div>
</template>

<style>
.shelf {
    display: flex;
    flex-direction: row;
}
</style>
