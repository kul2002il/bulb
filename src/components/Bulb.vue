<template>
    <div class="bulb">
        <div
            v-for="ball in data.balls"
            class="ball"
            :style="'background-color: ' + ball.color"
        ></div>
    </div>
</template>

<script>
export default {
    name: 'Bulb',
    props: [
        'data',
    ]
}
</script>

<style scoped>
.bulb {
    display: inline-block;
    border: 2px solid black;
    border-top-color: #e3e2e2;
    padding: 10px;
    margin: 5px;
    border-radius: 0 0 25px 25px;
}

.ball {
    width: 20px;
    height: 20px;
    margin: 2px;
    border: 2px solid black;
    border-radius: 10px;
}
</style>