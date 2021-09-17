<template>
<div class="container">

    <div class="panel scores">
        <div class="single-score">
            <h1 class="single-score__title">Player</h1>
            <div class="single-score__life-bar">
                <div
                    class="single-score__life-bar__health-point"
                    :class="{danger: playerLife < 20}"
                    :style="{width: playerLife + '%'}"
                />
            </div>
            <div> {{ playerLife}} </div>
        </div>

        <div class="single-score">
            <h1 class="single-score__title">Enemy</h1>
            <div class="single-score__life-bar">
                <div
                    class="single-score__life-bar__health-point"
                    :class="{danger: enemyLife < 20}"
                    :style="{width: enemyLife + '%'}"
                />
            </div>
            <div> {{ enemyLife}} </div>
        </div>
    </div>

    <div v-if="hasResult" class="panel result-panel">
        <div v-if=" enemyLife == 0 " class="win">You win!</div>
        <div v-else class="lose">You lose!</div>
    </div>

    <div class="panel buttons">
        <div v-if="running">
            <button class="btn attack" @click="attack(false)">Attack</button>
            <button class="btn special-attack" @click="attack(true)">Special attack</button>
            <button class="btn heal" @click="healAndHurt">Heal</button>
            <button class="btn give-up" @click="running = false">Escape</button>
        </div>
        <button v-else class="btn new-game" @click="startGame">New game</button>
    </div>

    <div v-if="logs.length" class="panel logs">
        <ul>
            <li class="log" :class="log.cls" v-for="log in logs" :key="log.text">
            {{ log.text }}
            </li>
        </ul>
    </div>

</div>
</template>


<style scoped>
.container {
    display: flex;
    flex-direction: column;
}

.panel {
    margin: 0.5rem;
    padding: 1rem;
    box-shadow: 0 0.2rem 1rem rgba(0, 0, 0, 0.15);
}

.scores{
    display: flex;
}

.single-score {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.single-score__title {
    font-weight: 600;
    font-size: 1.8rem;
}

.single-score__life-bar {
    width: 80%;
    height: 1.5rem;
    border: 1px solid #AAA;
    border-radius: 1rem;
}

.single-score__life-bar__health-point {
    display: flex;
    justify-content: center;
    height: 100%;
    border-radius: 1rem;
    background-color: seagreen;
}

.single-score__life-bar__health-point .danger {
    background-color: red;
}

/* RESULTS */
.result {
    display: flex;
    justify-content: center;
    font-size: 1.3rem;
    font-weight: 600;
}

.result .win {
    color: green;
}

.result .lose {
    color: red;
}

/* BUTTONS */
.buttons {
    display: flex;
    justify-content: center;
}

.btn {
    padding: 0.5rem 1rem;
    margin: 0 0.1rem;
    border-radius: 0.5rem;
    text-transform: uppercase;
    font-size: 1.2rem;
}

.new-game {
    background-color: indigo;
    color: white;
}

.attack {
    background-color: lightcoral;
    color: white;
}

.give-up {
    background-color: steelblue;
    color: white;
}

.special-attack {
    background-color: orangered;
    color: white;
}

.heal {
    background-color: lightskyblue;
    color: white;
}

/* LOGS */

.logs ul {
    display: flex;
    flex-direction: column;
    list-style: none;
    padding: 0;
}

.logs ul li {
    display: flex;
    justify-content: center;
    margin: 4px 0px;
    padding: 3px 0px;
    font-weight: 400;
    font-size: 1.1rem;
    text-transform: uppercase;
    border-radius: 2px;
}

.player {
    background-color: teal;
    color: white;
}

.enemy {
    background-color: brown;
    color: white;
}
</style>
