<template>
    <div id="info">
        <div style="max-width: 10%; margin-left: 5%;">
            <button class="icon" v-on:click="voltar" style="cursor: pointer;"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
            </button>
        </div>

        <div class="title">
            <font-awesome-icon icon="fa-solid fa-circle-info" class="icon" /> <h1 class="titleh1">Informações Úteis</h1>
        </div>

        <div class="text">
            <h1 class="title3">-INFORME COORDENAÇÃO TÉCNICA</h1>
            <br>
            <p style="font-weight: bold;">- Modalidades que não entraram no sorteio:</p>
            Dama, Xadrez, Atletismo e Natação
            <br><br><br>
            <b>-DAMA:</b>
            <br>
            Congresso técnico para definir forma de disputa
            <br>
            Data: 07/09/2023
            <br>
            Horário: 15h00
            <br>
            Local: APCEF/BA
            <br><br><br>
            <b>-XADREZ:</b>
            <br>
            Congresso técnico para definir forma de disputa
            <br>
            Data: 07/09/2023
            <br>
            Horário: 15h30
            <br>
            Local: APCEF/ BA
            <br><br><br>
            <b>-ATLETISMO:</b>
            <br>
            Corrida rústica 
            <br>
            Data: 08/09/2023
            <br>
            Horário: 07h30
            <br>
            Local: APCE/BA
            <br><br>
            INSCRIÇÕES DE ATLETAS NAS RESPECTIVAS FAIXAS: até  29/08/2023
            <br><br><br>
            <b>-ATLETISMO PISTA:</b>
            <br>
            Data: 09/09/2023
            <br>
            Horário: 07h30
            <br>
            Local: UFBA
            <br><br>
            INSCRIÇÕES DE ATLETAS NAS RESPECTIVAS PROVAS: até 29/08/2023
            <br><br><br>
            <b>-NATAÇÃO:</b>
            <br>
            Data: 09/09/2023
            <br>
            Horário: 14h00
            <br>
            Local: APCEF/BA
            <br><br><br>
            <b class="inf">INSCRIÇÕES: até 29/08/2023</b>
            <br>
            <b class="inf">BALIZAMENTO: até 08/09/2023</b>
            <br><br>
        </div>

        <div class="text">
            <h1 class="title3">-INFORMAÇÕES GERAIS</h1>
            <br>
            <h1 class="title2">Bolas</h1>
            <br>
            <p>
                Futebol Society - Penalty S11 
                <br><br>
                Futsal          - Penalty Max1000
                <br><br>
                Voleibol        - Mikasa v200w 
                <br><br>
                Vôlei de praia  - Mikasa VLS300 
                <br><br>
                Tênis           - Wilson 
                <br><br>
                Basquete        - Penalty BT 7.6 
                <br>
            </p>
        </div>

        <div class="text" style="margin-bottom: 100px;">
            <h1 class="title2">Hotéis</h1>
            <br>
            <p>
                <b>APCEF/AL</b>
                <br>
                Mais Hotel
                <br><br>
                Endereço: R. João Chagas Ortins de Freitas, 577 - Lot. Miragem, Lauro de Freitas - BA, 42710-610
                <br>
                Telefone: (71) 3612-7200
                <br><br><br><br>
                <b>APCEF/BA</b>
                <br>
                ibis Salvador Aeroporto Hangar
                <br>
                Endereço: Av. Luís Viana Filho, 13145 - São Cristóvão, Salvador - BA, 41500-300
                <br>
                Telefone: (71) 3505-2200
                <br><br><br><br>
                <b>APCEF/CE</b>
                <br>
                Hotel Intercity Salvador Aeroporto
                <br>
                Endereço: da Estrada do Coco 1,5, Av. Santos Dumont, 1883 - Santos Dumont, Salvador - BA, 42700-000
                <br>
                Telefone: (71) 3311-2700
                <br><br><br><br>
                <b>APCEF/MA</b>
                <br>
                Gran Hotel Stella Maris Urban Resort & Conventions
                <br>
                Endereço: Praça Stella Maris, 200 - Stella Maris, Salvador - BA, 41600-500
                <br>
                Horas: 
                <br>
                Aberto 24 horas
                <br>
                Telefone: (71) 3413-0000
                <br><br><br><br>
                <b>APCEF/PB</b>
                <br>
                Gran Hotel Stella Maris Urban Resort & Conventions
                <br>
                Endereço: Praça Stella Maris, 200 - Stella Maris, Salvador - BA, 41600-500
                <br>
                Horas: 
                <br>
                Aberto 24 horas
                <br>
                Telefone: (71) 3413-0000
                <br><br><br><br>
                <b>APCEF/PE</b>
                <br>
                Catussaba Resort Hotel
                <br>
                Endereço: Alamedas - Alameda Praia de Guaritá, S/N - Itapuã, Salvador - BA, 41600-460
                <br>
                Telefone: (71) 3374-8000
                <br><br><br><br>
                <b>APCEF/PI</b>
                <br>
                Novotel Salvador Hangar Aeroporto
                <br>
                Endereço: Av. Luís Viana Filho, 13 223 - São Cristóvão, Salvador - BA, 41500-300
                <br>
                Telefone: (71) 3505-4300
                <br><br><br><br>
                <b>APCEF/RN</b>
                <br>
                Malibu Plaza Hotel
                <br>
                Endereço: Av. Praia de Itapuã, 12 - quadra 19 lote 10 - Vilas do Atlântico, Lauro de Freitas - BA, 42700-000
                <br>
                Telefone: (71) 3026-4444
                <br><br><br><br>
                <b>APCEF/SE</b>
                <br>
                Catussaba Resort Hotel
                <br>
                Endereço: Alamedas - Alameda Praia de Guaritá, S/N - Itapuã, Salvador - BA, 41600-460
                <br>
                Telefone:  71 3374-8000
                <br>
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
        voltar() {
			location.reload();
		}
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
    margin-left: 4%;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 1.2rem;
    height: 20%;
    width: 100%;
}

.titleh1 {
    font-size: 2.2rem; 
    color: #163573;
    font-weight: 500;
}

.title2 {
    font-size: 1.3rem; 
    font-weight: 700;
}

.title3 {
    font-size: 1.5rem; 
    font-weight: bolder;
}


.text {
    margin-left: 6%;
    margin-right: 6%;
    margin-bottom: 7%;
    letter-spacing: 2px;
    text-align: justify;
    line-height: 1.3;
    color: #163573;
}

.icon {
    color: #163573;
    font-size: xxx-large;
    border: none;
	background: none;
	cursor: pointer;
}

.inf {
    font-size: .9rem;
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

    .title3 {
        font-size: 1.1rem; 
        font-weight: bolder;
    }
}
</style>
