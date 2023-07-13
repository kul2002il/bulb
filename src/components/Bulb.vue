<template>
    <div
        class="bulb"
        :class="{
            selected: selected,
        }"
    >
        <div
            v-for="ball in data.balls"
            class="ball"
            :style="'background-color: ' + ball.color"
        ></div>
        <div class="ball-wigth"></div>
    </div>
</template>

<script>
export default {
    name: 'Bulb',
    props: [
        'data',
        'selected',
    ]
}
</script>

<style scoped>
.bulb {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    border: 2px solid black;
    border-top-color: #e3e2e2;
    padding: 10px;
    margin: 5px;
    border-radius: 0 0 25px 25px;
}

.bulb.selected {
    position: relative;
    top: -10px;
}

.ball {
    width: 20px;
    height: 20px;
    margin: 2px;
    border: 2px solid black;
    border-radius: 10px;
}

.ball-wigth {
    width: 20px;
}
</style>