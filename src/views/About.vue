<template>
    <div id="about">
        <div style="max-width: 10%;">
            <button class="icon" v-on:click="voltar" style="cursor: pointer;"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
            </button>
        </div>

        <div class="title">
            <font-awesome-icon icon="fa-solid fa-circle-question" class="icon" /> <h1 style="font-size: 3rem; color: #163573; font-weight: 500;">Sobre</h1>
        </div>

        <div class="text">
            <p>
                Prezados atletas, <br><br><br>

                Com emoção e gratidão, damos as boas-vindas a todos vocês aos Jogos Regionais do Nordeste de 2023, um evento de resiliência, superação e reencontros após três anos de espera. Nestas páginas, convidamos vocês a se unirem a nós nessa jornada de paixão pelo esporte, marcada por aprendizados, amizades e conquistas. <br><br>

                Após um período de ausência, em virtude dos desafios impostos pela pandemia de COVID-19, temos a alegria de anunciar que os Jogos Regionais do Nordeste estão de volta, mais fortes e inspiradores do que nunca. A parceria entre a APCEF/BA (Associação do Pessoal da Caixa Econômica Federal da Bahia) e a Fenae (Federação Nacional das Associações do Pessoal da Caixa) garante a realização deste evento grandioso na Bahia, que sediará pela primeira vez essa festa do esporte em suas terras acolhedoras.
                Neste momento, nossos corações se enchem de esperança e ansiedade para abraçá-los e reencontrá-los em meio a uma atmosfera única de competição saudável e camaradagem. Cada passo dado no solo baiano será símbolo de recomeço, de um novo ciclo de determinação e dedicação ao esporte que amamos. <br><br>

                Ao longo destes dias de competição, estaremos unidos em um só propósito: celebrar a força e o talento do Nordeste no cenário esportivo nacional. Juntos, somos a energia que impulsiona cada prova, o coro que ecoa nas arquibancadas e a motivação que conduzirá cada um de vocês a dar o seu melhor.
                Que a essência dos Jogos Regionais do Nordeste, representada pela coragem e perseverança de cada atleta, esteja presente em cada momento vivido. Que os aplausos, a vibração e o calor humano da torcida fortaleçam cada passo rumo à vitória. Que a convivência fraterna e os novos laços formados sejam lembranças eternas desta jornada inesquecível.
                Que este guia, repleto de informações valiosas, possa acompanhá-los na jornada esportiva mais aguardada. Leiam, explorem e absorvam cada detalhe, pois ele foi preparado com carinho para tornar sua experiência única e proveitosa. <br><br>

                Desejamos a todos os atletas, técnicos e equipes uma competição memorável, repleta de emoções e conquistas. Que a grandeza do Nordeste se manifeste em cada performance, em cada lance e em cada vitória alcançada.
                Sintam-se em casa, sintam-se parte deste momento histórico. Boa sorte e bem-vindos ao palco dos Jogos Regionais do Nordeste de 2023!
                Com carinho e entusiasmo <br><br>

                John Ralph
                Presidente da APCEF/BA
            </p>
        </div>
    </div>
</template>

<script>

export default {
    components: {
    },
    name: "about-site",
    data() {
        return {
            page: "",
            id_modality: null,
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
#about {
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

.text {
    margin: 6%;
    margin-top: 2%;
    margin-bottom: 7%;
    letter-spacing: 2px;
    text-align: justify;
    line-height: 1.3;
    color: #163573;
    font-weight: light;
}

.icon {
    color: #163573;
    font-size: xxx-large;
    border: none;
	background: none;
	cursor: pointer;
}

@media (pointer:coarse) {
    #about {
        background-color: white;
        left: 0%;
        transform: translateX(0%);
        width: 100vw;
    }

    p {
        padding: 40px;
        letter-spacing: 2px;
        text-align: justify;
        text-justify: inter-word;
        height: 90%;
        margin-bottom: 10%;
        line-height: 1.2;
    }
}
</style>
