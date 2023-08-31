<template>
    <div id="regulation">
        <div style="max-width: 10%; margin-left: 5%;">
            <button class="icon" v-on:click="voltar" style="cursor: pointer;"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
            </button>
        </div>

        <div class="title">
            <font-awesome-icon icon="fa-solid fa-file-contract" class="icon" />
            <h1 class="titleh1">Regulamentos</h1>
        </div>

        <div class="text">
            <a href="/regulations/geral.pdf" alt="Regulamento Geral" target="_blank" rel="noopener noreferrer">
                Regulamento Geral
            </a>
            <br>
            <a href="/regulations/atletismo.pdf" alt="Regulamento de Atletismo" target="_blank" rel="noopener noreferrer">
                Regulamento Atletismo
            </a>
            <br>
            <a href="/regulations/basquete.pdf" alt="Regulamento de Basquete" target="_blank" rel="noopener noreferrer">
                Regulamento Basquete
            </a>
            <br>
            <a href="/regulations/beach_tenis.pdf" alt="Regulamento de Beach Tennis" target="_blank" rel="noopener noreferrer">
                Regulamento Beach Tênis
            </a>
            <br>
            <a href="/regulations/canastra.pdf" alt="Regulamento de Canastra" target="_blank" rel="noopener noreferrer">
                Regulamento Canastra
            </a>
            <br>
            <a href="/regulations/damas.pdf" alt="Regulamento de Damas" target="_blank" rel="noopener noreferrer">
                Regulamento Damas
            </a>
            <br>
            <a href="/regulations/domino.pdf" alt="Regulamento de Dominó" target="_blank" rel="noopener noreferrer">
                Regulamento Dominó
            </a>
            <br>
            <a href="/regulations/futebol.pdf" alt="Regulamento de Futebol" target="_blank" rel="noopener noreferrer">
                Regulamento Futebol
            </a>
            <br>
            <a href="/regulations/futsal.pdf" alt="Regulamento de Futsal" target="_blank" rel="noopener noreferrer">
                Regulamento Futsal
            </a>
            <br>
            <a href="/regulations/natacao.pdf" alt="Regulamento de Natação" target="_blank" rel="noopener noreferrer">
                Regulamento Natação
            </a>
            <br>
            <a href="/regulations/sinuca.pdf" alt="Regulamento de Sinuca" target="_blank" rel="noopener noreferrer">
                Regulamento Sinuca
            </a>
            <br>
            <a href="/regulations/tenis_mesa.pdf" alt="Regulamento de Tênis de Mesa" target="_blank" rel="noopener noreferrer">
                Regulamento Tênis de Mesa
            </a>
            <br>
            <a href="/regulations/tenis.pdf" alt="Regulamento de Tênis" target="_blank" rel="noopener noreferrer">
                Regulamento Tênis
            </a>
            <br>
            <a href="/regulations/volei_praia.pdf" alt="Regulamento de Vôlei de Praia" target="_blank" rel="noopener noreferrer">
                Regulamento Vôlei de Praia
            </a>
            <br>
            <a href="/regulations/volei.pdf" alt="Regulamento de Vôlei" target="_blank" rel="noopener noreferrer">
                Regulamento Vôlei
            </a>
            <br>
            <a href="/regulations/xadrez.pdf" alt="Regulamento de Xadrez" target="_blank" rel="noopener noreferrer">
                Regulamento Xadrez
            </a>
        </div>
        <br><br>
    </div>
</template>

<script>

export default {
    props: ["id_modality"],
    components: {
    },
    name: "regulation-site",
    data() {
        return {
            files: [],
        };
    },
    methods: {
        voltar() {
            location.reload();
        }
    },
}
</script>

<style scoped>
#regulation {
    background-color: white;
    position: fixed;
    display: inline;
    align-items: start;
    justify-content: flex-start;
    height: 90%;
    left: 50%;
    transform: translateX(-50%);
    width: 50vw;
    overflow-y: auto;
    overflow-x: hidden;
}

.title {
    margin-left: 6%;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 1.5rem;
    height: 20%;
    width: 100%;
}

.titleh1 {
    font-size: 2.2rem;
    color: #163573;
    font-weight: 500;
}


.text {
    margin-left: 6%;
    margin-right: 6%;
    margin-bottom: 7%;
    letter-spacing: 1px;
    text-align: justify;
    line-height: 1.6;
    color: #163573;
}

.icon {
    color: #163573;
    font-size: xxx-large;
    border: none;
	background: none;
	cursor: pointer;
}

@media (pointer:coarse) {
    #regulation {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100vw;
    }

    .title {
        font-size: 14%;
    }
}
</style>
