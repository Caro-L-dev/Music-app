<script>
export default {
    name: 'Game',
    data() {
        return {
            playerLife: 100,
            opponentLife: 100,
            running: false,
            logs: []
        }
    },
    computed: {
        hasResult () {
            return this.playerLife == 0 || this.opponentLife == 0;
        }
    },
    methods: {
        startGame() {
            this.running = true
            this.playerLife = 100
            this.monsterLife = 100
            this.logs = []
        },
         attack(special) {
            this.hurt('opponentLife', 5, 10, special, 'Player', 'Opponent', 'Player')
            if (this.monsterLife > 0)
                this.hurt('playerLife', 7, 12, false, 'Opponent', 'Player', 'Opponent')
        },
        hurt(atr, min, max, special, source, target, cls) {
            const plus = special ? 5 : 0
            const hurt = this.getRandom(min + plus, max + plus)
            this[atr] = Math.max(this[atr] - hurt, 0)
            this.registerLog(`${source} attack ${target} and inflict ${hurt} damage.`, cls)
        },
        healAndHurt() {
            this.heal(10, 15)
            this.hurt('playerLife', 7, 12, false, 'Opponent', 'Player', 'Opponent')
        },
        heal(min, max) {
            const heal = this.getRandom(min, max)
            this.playerLife = Math.min(this.playerLife + heal, 100)
            this.registerLog(`Player recovers  ${heal} health points.`, 'player')
        },
         getRandom(min, max) {
            const value = Math.random() * (max - min) + min
            return Math.round(value)
        },
        registerLog(text, cls) {
            this.logs.unshift({text, cls})
        },
    },
    watch: {
        hasResult(value) {
            if (value) this.running = false
        }
    }

}
</script>


<template>
<div class="container">

    <div class="panel scores">
        <div class="single-score">
            <div class="img" />
            <h1 class="single-score__title">Player</h1>
            <div class="single-score__life-bar">
                <div
                    class="single-score__life-bar__health-point"
                    :class="{danger: playerLife < 20}"
                    :style="{width: playerLife + '%'}"
                />
            </div>
            <div class="single-score__life"> {{ playerLife }} </div>
        </div>

        <div class="single-score">
            <div class="img" />
            <h1 class="single-score__title">opponent</h1>
            <div class="single-score__life-bar">
                <div
                    class="single-score__life-bar__health-point"
                    :class="{danger: opponentLife < 20}"
                    :style="{width: opponentLife + '%'}"
                />
            </div>
            <div class="single-score__life"> {{ opponentLife }} </div>
        </div>
    </div>

    <div v-if="hasResult" class="panel result-panel">
        <div v-if=" opponentLife == 0 " class="win">You win!</div>
        <div v-else class="lose">You lose!</div>
    </div>

    <div class="panel buttons">
        <div v-if="running">
            <button class="btn attack" @click="attack(false)">Attack</button>
            <button class="btn special-attack" @click="attack(true)">Special attack</button>
            <button class="btn heal" @click="healAndHurt">Heal</button>
            <button class="btn give-up" @click="running = false">Stop</button>
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
    font-family: sans-serif;
    letter-spacing: 0.2rem;
}

.panel {
    background-color: rgb(73, 73, 85);
    margin: 0.5rem;
    padding: 1rem;
    border-radius: 1rem;
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

.img {
    height: 4rem;
    width: 4rem;
    border-radius: 1rem;
}

.single-score__title {
    font-weight: 600;
    font-size: 1.8rem;
    text-transform: uppercase;
    margin: 1rem;

    background: linear-gradient(to bottom right, #D81E5D, #8a4FFF);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.single-score__life-bar {
    width: 80%;
    height: 1.5rem;
    border: 0.2rem solid #4ec943;
    background-color: #FF4500;
    border-radius: 1rem;
}

.single-score__life-bar__health-point {
    display: flex;
    justify-content: center;
    height: 100%;
    border-radius: 1rem;
    background-color: seagreen;
    transition: 0.4s ease-in-out;
}

.single-score__life {
    background-color: grey;
    color: white;
    margin: 1rem;
    padding: 0.5rem 5rem;
    border-radius: 3rem;
}

/* RESULTS */
.result {
    display: flex;
    justify-content: center;
    font-size: 1.3rem;
    font-weight: 600;
}

.win {
    color: #4EC943;
    text-align: center;
}

.lose {
    color: red;
}

/* BUTTONS */
.buttons {
    display: flex;
    justify-content: center;
}

.btn {
    cursor: pointer;
    padding: 0.5rem 1rem;
    margin: 0 0.2rem;
    border-radius: 0.5rem;
    text-transform: uppercase;
    font-weight: 700;
    font-size: 1.2rem;
    border: none;
    transition: 0.4s ease-in-out;
    color: white;
    background: linear-gradient(to bottom right, #D81E5D, #8a4FFF);
}

.btn:hover {
    background: linear-gradient(to bottom right, #c01a51, #7643db);
}
/* LOGS */

.logs ul {
    display: flex;
    flex-direction: column;
    list-style: none;
    padding: 0;
    color: white;
}

.logs ul li {
    display: flex;
    justify-content: center;
    margin: 4px 0px;
    padding: 3px 0px;
    font-weight: 400;
    font-size: 1.1rem;
    border-radius: 2px;
}

.player {
    background-color: teal;
    color: white;
}

.opponent {
    background-color: brown;
    color: white;
}
</style>
