<template>
    <div id="home">
        <div class='row'>
            <a href="#" @click="page = 'modality'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-volleyball" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Tabela de Jogos</p>
            </a>

            <a href="#" @click="page = 'modality'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-trophy" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Tabela de Pontos</p>
            </a>
        </div>

        <div class='row'>
            <a href="#" @click="page = 'regulamento'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-file-contract" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Regulamento</p>
            </a>
            <a href="#" @click="page = 'guia'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-book-open" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Guia do Atleta</p>
            </a>
        </div>

        <div class='row'>
            <a href="#" @click="page = 'informacoes'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-circle-info" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Informações</p>
            </a>
            <a href="#" @click="page = 'sobre'">
                <div class="aux">
                    <div class="button">
                        <font-awesome-icon icon="fa-solid fa-circle-question" style="color: #ffffff;" class="icon" />
                    </div>
                </div>
                <p>Sobre</p>
            </a>
        </div>
    </div>

    <div class="modaldiv" v-if="page == 'modality'">
        <modal></modal>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion } from '@fortawesome/free-solid-svg-icons'
library.add(faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion)
import modal from '../components/Modal.vue'

export default {
    components: {
        modal
    },
    name: "home-site",
    data() {
        return {
            page: "",
        };
    },
    methods: {
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
    padding-top: 10vh;
}

.row {
    display: flex;
    align-items: center;
    justify-content: center;
    /* margin-top: 50px; */
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
    /* justify-content: center; */
    /* align-items: center; */
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
