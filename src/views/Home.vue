<template>
    <div id="home">
        <div id="buttons">
            <div class='column'>
                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-volleyball" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Tabela de Jogos</p>

                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-file-contract" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Regulamento</p>
                
                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-circle-info" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Informações</p>
            </div>

            <div class='column'>
                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-trophy" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Tabela de Pontos</p>

                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-book-open" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Guia do Atleta</p>

                <button>
                    <div class="aux">
                        <div class="button">
                            <font-awesome-icon icon="fa-solid fa-circle-question" style="color: #ffffff;" class="icon" />
                        </div>
                    </div>
                </button>
                <p>Sobre</p>
            </div>
        </div>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion } from '@fortawesome/free-solid-svg-icons'
library.add(faVolleyball, faTrophy, faFileContract, faBookOpen, faCircleInfo, faCircleQuestion)

export default {
    components: {
    },
    name: "home-site"
}
</script>

<style scoped>

#home {
    background-color: white;
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 50%;
    transform: translateX(-50%);
    width: 50%;
    height: 100vh;
    padding-top: 10vh;
}

#buttons {
    display: flex;
    height: 90%;
    width: 100%;
}

.column {
    display: grid;
    justify-content: center;
    height: 90%;
    width: 100%;
    margin-top: 50px;
}

.aux {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    height: 100%;
    width: 100%;
}

.icon {
    min-height: 80%;
    min-width: 80%;
}

.button {
    background-color: #163573;
    border-radius: 10%;
    height: 60%;
    width: 60%;
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

button {
    background-color: #ffffff;
    border: none;
}

@media (pointer:coarse) { 
    #home {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100%;
    }
}

</style>
