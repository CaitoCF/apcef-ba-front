<template>
    <div id="points">
        <div class="top">
            <header class="header">
                <button class="icon" v-on:click="voltar"><font-awesome-icon icon="fa-solid fa-arrow-left"
                        style="color: #163573; height: 30px; width: 30px;" />
                </button>
                <h1 class="titleh1">Tabelas de Pontos</h1>
            </header>
        </div>

        <div class="mid">
            <header class="header" style="gap: 1rem; margin-top: 6%;">
                <font-awesome-icon icon="fa-solid fa-trophy" style="color: #163573;" class="icon" />
                Pontuação Final
            </header>

            <div class="table-final">
                <table class="tb">
                    <thead>
                        <th v-for="(item, index) in header" :key="index">{{ item }}</th>
                    </thead>
                    <tbody>
                        <tr v-for="(item, index) in modalities" :key="index">
                            <td class="modalidade">{{ item.modalityName }}</td>
                            <td v-for="(item2, index) in item.pointsPerDivisions" :key="index">{{ item2.points }}</td>
                            <td style="font-weight: bolder;">{{ item.total }}</td>
                        </tr>
                        <tr style="font-style: italic; font-weight: bolder;">
                            <td class="modalidade">TOTAL</td>
                            <td v-for="(item, index) in footer" :key="index">{{ item.points }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <hr>

            <header class="header" style="gap: 1rem; margin-top: 3%;">
                <font-awesome-icon icon="fa-solid fa-ranking-star" style="color: #163573;" class="icon" />
                Classificação Final
            </header>

            <div class="table-final">
                <table class="tb">
                    <thead>
                        <th v-for="(item, index) in header2" :key="index">{{ item }}</th>
                    </thead>
                    <tbody>
                        <tr v-for="(item, index) in classification" :key="index">
                            <td class="modalidade">{{ item.order }}º</td>
                            <td class="modalidade">{{ item.divisionName }}</td>
                            <td>{{ item.colPoints }}</td>
                            <td>{{ item.dupPoints }}</td>
                            <td>{{ item.indPoints }}</td>
                            <td>{{ item.atlPoints }}</td>
                            <td>{{ item.natPoints }}</td>
                            <td style="font-weight: bolder;">{{ item.totalPointPerPosition }}</td>
                        </tr>
                        <tr style="font-style: italic; font-weight: bolder;">
                            <td v-for="(item, index) in footer2" :key="index">{{ item }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { } from '@fortawesome/free-solid-svg-icons';
library.add();
import axios from 'axios';

export default {
    props: ["id_modality"],
    components: {
    },
    name: "points-site",
    data() {
        return {
            header: ['', 'AL', 'BA', 'CE', 'MA', 'PB', 'PE', 'PI', 'RN', 'SE', 'TOTAL'],
            header2: ['POS', 'APCEF', 'COLETIVAS', 'DUPLAS', 'INDIVIDUAIS', 'ATLETISMO', 'NATAÇÃO', 'TOTAL'],
            footer: [],
            footer2: [],
            modalities: [],
            classification: [],
        };
    },
    methods: {
        voltar() {
            location.reload();
        },
        somarArray(array) {
            return array.reduce(function (acumulador, elemento) {
                return acumulador + elemento;
            }, 0);
        },
    },
    async mounted() {
        let res = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/points/final-table');
        let finalPoints = res.data;        
        this.modalities = finalPoints.body;
        this.modalities.forEach((element) => {
            let sum = 0;
            element.pointsPerDivisions.forEach((e) => {
                sum += e.points;
            });
            element.total = sum;
        });
        this.footer = finalPoints.footer;

        let res2 = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/points/final-score');
        this.classification = res2.data.scoreRows;

        const arrayColumn = (array, column) => {
            return array.map(item => item[column]);
        };

        let colPoints = arrayColumn(this.classification, 'colPoints');
        this.classification.colTotal = this.somarArray(colPoints);
        let dupPoints = arrayColumn(this.classification, 'dupPoints');
        this.classification.dupTotal = this.somarArray(dupPoints);
        let indPoints = arrayColumn(this.classification, 'indPoints');
        this.classification.indTotal = this.somarArray(indPoints);
        let atlPoints = arrayColumn(this.classification, 'atlPoints');
        this.classification.atlTotal = this.somarArray(atlPoints);
        let natPoints = arrayColumn(this.classification, 'natPoints');
        this.classification.natTotal = this.somarArray(natPoints);

        this.footer2 = ['', 'TOTAL', this.classification.colTotal, this.classification.dupTotal, this.classification.indTotal, this.classification.atlTotal, this.classification.natTotal];
    }
}
</script>

<style scoped>
#points {
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
	width: 96%;
	border: 1px solid #163573;
	margin-top: 1%;
    position: relative;
    margin-left: 2%;
}

#aux1 {
    display: flex;
}

.top {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50vw;
    height: 10vh;
    gap: 2rem;
}

.mid {
    width: 50vw;
    height: 80%;
    display: grid;
    overflow: auto;
}

.header {
    padding: 15px;
    display: flex;
    color: #163573;
    justify-content: flex-start;
    font-weight: bold;
    font-size: large;
    width: 100%;
    gap: 2rem;
}

.icon {
    border: none;
    background: none;
    cursor: pointer;
}

table {
    border: solid #163573;
    border-collapse: collapse;
}

th {
    border-bottom: solid #163573;
    border-left: solid #163573;
    font-weight: bold;
}

tr {
    border-bottom: solid #163573;
}

td {
    border-right: solid #163573;
    text-align: center;
    vertical-align: middle;
}

.modalidade {
    font-weight: bold;
}

.tb {
    width: 100%;
}

.table-final {
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 15px;
    margin-bottom: 70px;
}

@media (pointer:coarse) {
    #points {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100vw;
    }

    .top {
        width: 100vw;
        justify-content: flex-start;
        gap: 0rem;
    }

    .mid {
        width: 100vw;
        height: 75%;
        display: grid;
        overflow: auto;
    }

    .titleh1 {
        font-size: xx-large;
    }
}
</style>
