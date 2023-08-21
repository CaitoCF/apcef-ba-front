<template>
    <div id="info">
        <div class="title">
            <font-awesome-icon icon="fa-solid fa-circle-info" class="icon" /> <h1 class="titleh1">Informações Úteis</h1>
        </div>

        <div class="text">
            <h1 class="title2">Informações Técnicas</h1>
            <br>
            <p>
                Natação: <br>
                - Provas 09/09/2023 sábado, às 14h <br>
                <br>
                Atletismo: <br>
                - Provas 09/09/2023 sábado, às 8h <br>
                <br>
                Corrida Rústica: <br>
                - 08/09/2023, sexta-feira, às 7h <br>
                <br>
                Xadrez: <br>
                - Congresso Técnico será realizado no dia xx xx <br>
                <br>
                Damas: <br>
                - Congresso Técnico será realizado no dia xxxx <br>
            </p>
        </div>

        <div class="text">
            <h1 class="title2">Bolas</h1>
            <br>
            <p>
                Futebol Society - Penalty S11 <br>
                <br>
                Futsal          - Penalty Max1000 <br>
                <br>
                Voleibol        - Mikasa v200w <br>
                <br>
                Vôlei de praia  - Mikasa VLS300 <br>
                <br>
                Tênis           - Wilson <br>
                <br>
                Basquete        - Penalty BT 7.6 <br>
            </p>
        </div>

        <div class="text">
            <h1 class="title2">Hotéis</h1>
            <br>
            <p>
                Os hotéis que hospedarão as delegações nos Jogos Regionais do Nordeste da Fenae 2023, de 06/09/2023 a 10/09/2023.
            </p>
        </div>
        <br><br>
    </div>
</template>

<script>

export default {
    components: {
    },
    name: "info-site",
    data() {
        return {
            page: "",
            id_modality: null,
        };
    },
    methods: {

    },
}
</script>

<style scoped>
#info {
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

.title2 {
    font-size: 1.5rem; 
    font-weight: 700;
}

.text {
    margin-left: 6%;
    margin-right: 6%;
    margin-bottom: 7%;
    letter-spacing: 2px;
    text-align: justify;
    line-height: 1.3;
    color: #163573;
    font-weight: bold;
}

.icon {
    color: #163573;
    font-size: xxx-large;
}

p {
    font-size: 1rem;
    font-weight: 500;
}

@media (pointer:coarse) {
    #info {
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
