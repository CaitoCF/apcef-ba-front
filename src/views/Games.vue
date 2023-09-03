<template>
	<div id="games">
		<div v-if="modality_name == null">
			<div class="top">
				<div class="aux">
					<header class="header">
						<div style="margin-right: 20px;">
							<button class="icon" v-on:click="voltar"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
							</button>
						</div>
						<slot name="header">
							Selecione a Rodada:
						</slot>
					</header>

					<div class="select">
						<section class="body">
							<select name="rodada" v-model="id_round">
								<option :value="item.id" v-for="(item, index) in rounds" :key="index">
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

			<div class="mid" style="padding-bottom: 50px;">
				<div class='row' v-for="(item, index) in games" :key="index">
					<div class="info">
						<h5 style="color: #163573;">Local: {{ item.placeName }}</h5>
						<h5 style="color: #163573;">{{ dataAtualFormatada(item.matchDate) }}</h5>
					</div>
					<div class="game">
						<div class="box little-box">{{ item.order }}</div>
						<div class="box team">{{ item.firstTeamName }}</div>
						<div class="box little-box">{{ item.firstTeamScore }}</div>
						<h2 style="color: #163573;">X</h2>
						<div class="box little-box">{{ item.secondTeamScore }}</div>
						<div class="box team">{{ item.secondTeamName }}</div>
					</div>
					<hr>
				</div>
			</div>
		</div>
		<div v-else>
			<div class="top2">
				<div class="aux">
					<header class="header2">
						<div style="margin-right: 20px;">
							<button class="icon" v-on:click="voltar"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
							</button>
						</div>
					</header>
				</div>
			</div>
			<div v-if="modality_name == 'Dama'" class="table-final">
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">FORMA DE DISPUTA: Será definida no Congresso Técnico</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data do Congresso Técnico:</b> 07/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 14h30m
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
			</div>
			<div v-if="modality_name == 'Atletismo'" class="table-final" style="display: flex; flex-direction: column; gap: 3rem; margin-top: 100px;">
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">CONGRESSO TÉCNICO</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> 07/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 16h00
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">CORRISA RÚSTICA</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> 08/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 7h30m
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">PROVAS DE PISTA</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> 09/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 7h30m
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b>UFBA
							</td>
						</tr>
					</tbody>
				</table>
			</div>
			<div v-if="modality_name == 'Xadrez'" class="table-final">
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">FORMA DE DISPUTA: Será definida no Congresso Técnico</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data do Congresso Técnico:</b> 07/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 15h00
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
			</div>
			<div v-if="modality_name == 'Natação'" class="table-final" style="display: flex; flex-direction: column; gap: 3rem; margin-top: 100px;">
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">CONGRESSO TÉCNICO</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> 08/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 16h00
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">PROVAS</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> 09/09/2023
							</td>
						</tr>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Horário:</b> 14h00
							</td>
						</tr>
						<tr>
							<td>
								<b>Local:</b> APCEF/BA
							</td>
						</tr>
					</tbody>
				</table>
				<table style="border: solid 2px #163573;">
					<thead>
						<th style="border-bottom: solid 2px #163573; padding: 10px;">BALIZAMENTO</th>
					</thead>
					<tbody>
						<tr>
							<td style="border-bottom: solid 2px #163573;">
								<b>Data:</b> até 01/09/2023
							</td>
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
	name: "games-site",
	data() {
		return {
			id_round: null,
			rounds: [],
			games: [],
			modality_name: null,
		};
	},
	methods: {
		select_round(item) {
			this.id_round = item;
		},
		async pesquisar() {
			let res = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/rounds/matches?RoundId=' + this.id_round + '&ModalityId=' + this.id_modality);
			this.games = res.data;
			this.games.forEach(this.check_team);
		},
		voltar() {
			location.reload();
		},
		dataAtualFormatada(item) {
			var data = new Date(item);
			let dia  = data.getDate().toString();
			let diaF = (dia.length == 1) ? '0'+dia : dia;
			let mes  = (data.getMonth()+1).toString();
			let mesF = (mes.length == 1) ? '0'+mes : mes;
			let hora = data.getHours().toString();
			let horaF = (hora.length == 1) ? '0'+hora : hora;
			let minuto = data.getMinutes().toString();
			let minutoF = (minuto.length == 1) ? '0'+minuto : minuto;
			return diaF+"/"+mesF+' '+horaF+':'+minutoF;
		},
		async check_team(game) {
			if (game.firstTeamName == 'A definir' || game.secondTeamName == 'A definir') {
				let response = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/modalities');
				let modalities = response.data;
				let modality = modalities.find((element) => element.id == this.id_modality).name;
				switch (modality) {
					case 'Basquete':
					case 'Tênis mesa masc':
						switch(game.order) {
							case 13:
								game.firstTeamName = '2º Grupo A';
								game.secondTeamName = '2º Grupo B';
								break;
							case 14:
								game.firstTeamName = '1º Grupo A';
								game.secondTeamName = '1º Grupo B';
								break;
						}
						break;
					case 'Beach tennis':
					case 'Canastra':
					case 'Dominó':
					case 'Fut livre':
					case 'Fut master':
					case 'Futsal masculino':
					case 'Tênis masculino':
					case 'Vôlei praia masc':
						switch(game.order) {
							case 4:
								game.secondTeamName = 'Perd jg 1';
								break;
							case 5:
								game.secondTeamName = 'Perd jg 2';
								break;
							case 6:
								game.secondTeamName = 'Perd jg 3';
								break;
							case 7:
								game.secondTeamName = 'Venc jg 1';
								break;
							case 8:
								game.secondTeamName = 'Venc jg 2';
								break;
							case 9:
								game.secondTeamName = 'Venc jg 3';
								break;
							case 10:
								game.firstTeamName = '1º Grupo A';
								game.secondTeamName = '1º Grupo B';
								break;
							case 11:
								game.firstTeamName = '1º Grupo C';
								game.secondTeamName = '2º Melhor Col.';
								break;
							case 12:
								game.firstTeamName = 'Perd jg 10';
								game.secondTeamName = 'Perd jg 11';
								break;
							case 13:
								game.firstTeamName = 'Venc jg 10';
								game.secondTeamName = 'Venc jg 11';
								break;
						}
						break;
					case 'Futsal feminino':
					case 'Sinuca':
					case 'Vôlei feminino':
					case 'Vôlei masculino':
					case 'Vôlei praia fem':
						switch(game.order) {
							case 6:
								game.secondTeamName = 'Perd jg 3';
								break;
							case 9:
								game.secondTeamName = 'Venc jg 3';
								break;
							case 10:
								game.firstTeamName = '2º Grupo A';
								game.secondTeamName = '2º Grupo B';
								break;
							case 11:
								game.firstTeamName = '1º Grupo A';
								game.secondTeamName = '1º Grupo B';
								break;
						}
						break;
					case 'Tênis dupla masc':
					case 'Tênis feminino':
					case 'Tênis mesa fem':
						switch(game.order) {
							case 3:
								game.secondTeamName = 'Perd jg 1';
								break;
							case 4:
								game.secondTeamName = 'Perd jg 2';
								break;
							case 5:
								game.secondTeamName = 'Venc jg 1';
								break;
							case 6:
								game.secondTeamName = 'Venc jg 2';
								break;
							case 7:
								game.firstTeamName = '2º Grupo A';
								game.secondTeamName = '2º Grupo B';
								break;
							case 8:
								game.firstTeamName = '1º Grupo A';
								game.secondTeamName = '1º Grupo B';
								break;
						}
						break;
				}
			}
		}
	},
	async mounted() {
		let response = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/rounds/' + this.id_modality);
		this.rounds = response.data;
		if (this.rounds.length == 0) {
			let modalities = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/modalities');
			modalities = modalities.data;
			let myModality = modalities.find((element) => {
				return element.id == this.id_modality;
			});
			this.modality_name = myModality.name;
		} else {
			this.id_round = this.rounds[0].id;
	
			let res = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/rounds/matches?RoundId=' + this.id_round + '&ModalityId=' + this.id_modality);
			this.games = res.data;
			this.games.forEach(this.check_team);
		}
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

.table-final {
    height: 20vh;
    width: 100%;
    display: flex;
    justify-content: center;
	align-items: center;
    padding: 15px;
}

hr {
	width: 90%;
	border: 1px solid #163573;
	margin-top: 1%;
}

table {
	border-collapse: collapse;
	width: 80%;
	height: 100%;
}

.top {
	display: flex;
	align-items: flex-end;
	justify-content: center;
	width: 50vw;
	height: 20vh;
	gap: 2rem;
}

.top2 {
	display: flex;
	align-items: center;
	justify-content: center;
	width: 50vw;
	height: 20vh;
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
	color: #163573;
	justify-content: flex-start;
	font-weight: bold;
	font-size: x-large;
	width: 100%;
}

.header2 {
	display: flex;
	color: #163573;
	justify-content: flex-start;
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
	cursor: pointer;
}

.icon {
	border: none;
	background: none;
	cursor: pointer;
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
	margin-bottom: 50px;
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
	align-items: center;
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

	.table-final {
		width: 100vw;
	}
}
</style>
