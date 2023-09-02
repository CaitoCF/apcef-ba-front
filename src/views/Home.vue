<template>
    <div id="home">
        <div class='row'>
            <a href="#" @click="modality = true, page = 'games'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-volleyball" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Tabela de Jogos</p>
            </a>

            <a href="#" @click="page = 'points'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-trophy" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Tabela de Pontos</p>
            </a>
        </div>

        <div class='row'>
            <a href="#" @click="modality = true, page = 'points_group'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-people-group" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Pontos por Grupo</p>
            </a>
            <a href="/guia_atleta.pdf" target="_blank">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-book-open" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Guia do Atleta</p>
            </a>
        </div>

        <div class='row'>
            <a href="#" @click="page = 'info'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-circle-info" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Informações</p>
            </a>
            <a href="#" @click="page = 'about'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-circle-question" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Sobre</p>
            </a>
        </div>

        <div class='row'>
            <a href="#" @click="page = 'regulation'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-file-contract" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Regulamentos</p>
            </a>
        </div>
    </div>

    <div class="modaldiv" v-if="modality == true">
        <modal @changed="select_modality"></modal>
    </div>

    <div v-if="page == 'games' && modality == false">
        <games :id_modality=id_modality></games>
    </div>

    <div v-if="page == 'points' && modality == false">
        <points :id_modality=id_modality></points>
    </div>

    <div v-if="page == 'points_group' && modality == false">
        <points_group :id_modality=id_modality></points_group>
    </div>

    <div v-if="page == 'regulation' && modality == false">
        <regulation :id_modality=id_modality></regulation>
    </div>

    <div v-if="page == 'info'">
        <info></info>
    </div>

    <div v-if="page == 'about'">
        <about></about>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion, faMagnifyingGlass, faArrowLeft, faRankingStar, faPeopleGroup } from '@fortawesome/free-solid-svg-icons';
library.add(faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion, faMagnifyingGlass, faArrowLeft, faRankingStar, faPeopleGroup);
import modal from '../components/Modal.vue';
import about from './About.vue';
import info from './Info.vue';
import games from './Games.vue';
import regulation from './Regulation.vue';
import points from './Points.vue';
import points_group from './PointsGroup.vue';

export default {
    components: {
        modal,
        about,
        info,
        games,
        regulation,
        points,
        points_group
    },
    name: "home-site",
    data() {
        return {
            page: "",
            id_modality: null,
            modality: false,
        };
    },
    methods: {
        select_modality(item) {
            this.id_modality = item;
            this.modality = false;
        }
    },
}
</script>

<style scoped>
#home {
    background-color: white;
    position: fixed;
    display: grid;
    align-items: center;
    justify-content: center;
    left: 50%;
    transform: translateX(-50%);
    width: 50vw;
    height: 100vh;
    padding-top: 14vh;
}

.row {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 4vw;
}

.aux {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    height: 100%;
    width: 100%;
}

.icon {
    height: 90%;
    width: 90%;
}

.button {
    background-color: #163573;
    border-radius: 10%;
    height: 10vh;
    width: 7vw;
    display: flex;
    justify-content: center;
    align-items: center;
}

p {
    margin-left: auto;
    margin-right: auto;
    color: #163573;
    font-weight: bold;
}

a {
    display: inline-grid;
    min-width: 80%;
    gap: 1rem;
    text-decoration: none;
}

.modaldiv {
    position: fixed;
    height: 100vh;
    width: 50vw;
    left: 25%;
}

@media (pointer:coarse) {
    #home {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100%;
    }

    .button {
        width: 20vw;
    }

    .modaldiv {
        width: 100vw;
        left: 0;
    }
}
</style>
