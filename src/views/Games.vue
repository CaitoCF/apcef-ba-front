<template>
    <div id="games">
        <div class="top">
            <div class="aux">
                <header class="header">
                    <slot name="header">
                        Selecione a Rodada:
                    </slot>
                </header>

                <div class="select">
                    <section class="body">
                        <select name="rodada" v-model="id_round">
                            <option :value="item.id" v-for="(item, index) in rodadas" :key="index">
                                {{ item.name }}
                            </option>
                        </select>
                    </section>
                </div>
            </div>

            <div class="search">
                <button class="icon" v-on:click="pesquisar"><font-awesome-icon icon="fa-solid fa-magnifying-glass"
                        style="color: #ffffff;" class="icon" />
                </button>
            </div>
        </div>

        <div class="mid">
            <div class='row' v-for="(item, index) in games" :key="index">
                <div class="info">
                    <h5 style="color: #163573;">Local: {{ item.local }}</h5>
                    <h5 style="color: #163573;">{{ item.date_time }}</h5>
                </div>
                <div class="game">
                    <div class="box little-box">{{ item.id }}</div>
                    <div class="box team">{{ item.team_1 }}</div>
                    <div class="box little-box">{{ item.team_1_points }}</div>
                    <h2 style="color: #163573;">X</h2>
                    <div class="box little-box">{{ item.team_2_points }}</div>
                    <div class="box team">{{ item.team_2 }}</div>
                </div>
                <hr>
            </div>
        </div>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { } from '@fortawesome/free-solid-svg-icons';
library.add();

export default {
    props: ["id_modality"],
    components: {
    },
    name: "games-site",
    data() {
        return {
            id_round: 1,
            rodadas: [],
            games: [],
        };
    },
    methods: {
        select_round(item) {
            this.id_round = item;
        },
        pesquisar(item) {
            console.log(item);
        },
    },
    async mounted() {
        this.rodadas = [
            { 'id': 1, 'name': 'Rodada 1' },
            { 'id': 2, 'name': 'Rodada 2' },
            { 'id': 3, 'name': 'Semifinal' },
            { 'id': 4, 'name': 'Final' },
        ];
        this.games = [
            { 'id': 1, 'team_1': 'time A', 'team_2': 'Time B', 'team_1_points': 0, 'team_2_points': 0, 'date_time': '09/09/2023 14:00', 'local': 'APCEF/BA' },
            { 'id': 2, 'team_1': 'time C', 'team_2': 'Time D', 'team_1_points': 0, 'team_2_points': 0, 'date_time': '09/09/2023 17:00', 'local': 'APCEF/BA' },
            { 'id': 3, 'team_1': 'time A', 'team_2': 'Time B', 'team_1_points': 0, 'team_2_points': 0, 'date_time': '09/09/2023 14:00', 'local': 'APCEF/BA' },
            { 'id': 4, 'team_1': 'time C', 'team_2': 'Time D', 'team_1_points': 0, 'team_2_points': 0, 'date_time': '09/09/2023 17:00', 'local': 'APCEF/BA' }
        ];
    }
}
</script>

<style scoped>
#games {
    background-color: white;
    position: fixed;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    left: 50%;
    transform: translateX(-50%);
    width: 50vw;
    height: 100vh;
}

hr {
    width: 90%;
    border: 1px solid #163573;
    margin-top: 1%;
}

.top {
    display: flex;
    align-items: flex-end;
    justify-content: center;
    width: 50vw;
    height: 20vh;
    gap: 2rem;
}

.mid {
    display: flex;
    flex-direction: column;
    width: 50vw;
    gap: 3rem;
    margin-top: 10%;
    overflow-y: auto;
    height: 60vh;
}

.header {
    padding: 15px;
    display: flex;
    position: relative;
    color: #163573;
    justify-content: space-between;
    font-weight: bold;
    font-size: x-large;
    width: 100%;
}

.body {
    position: relative;
    padding: 15px;
    width: 100%;
}

.search {
    background-color: green;
    padding: 10px;
    font-size: 20px;
    border-radius: 50%;
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.icon {
    border: none;
    background: none;
}

select {
    width: 100%;
    height: 3rem;
    background-color: #163573;
    color: white;
}

.select {
    width: 100%;
}

.aux {
    display: flex;
    flex-direction: column;
    width: 85%;
}

.row {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.game {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    gap: 1.5rem;
}

.box {
    background-color: #163573;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-weight: bold;
}

.team {
    height: 4vh;
    width: 30%;
    border-radius: 5%;
}

.little-box {
    height: 4vh;
    border-radius: 10%;
    width: 5%;
}

.info {
    margin-left: 8%;
    margin-bottom: 3%;
    display: flex;
    flex-direction: column;
    gap: .5rem;
}

@media (pointer:coarse) {
    #games {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100vw;
    }

    .aux {
        width: 85%;
    }

    .top {
        width: 100vw;
        justify-content: flex-start;
        gap: 0rem;
    }

    .mid {
        width: 100vw;
    }

    .little-box {
        width: 10%;
    }

    .game {
        gap: .5rem;
        padding: 2%;
    }

    .search {
        width: 10%;
        height: 25%;
    }

    hr {
        width: 90vw;
    }
}
</style>
