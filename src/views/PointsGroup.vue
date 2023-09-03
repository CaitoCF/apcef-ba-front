<template>
	<div id="pointsgroup">
		<div class="top">
			<div class="aux">
				<header class="header">
					<div style="margin-right: 20px;">
						<button class="icon" v-on:click="voltar"><font-awesome-icon icon="fa-solid fa-arrow-left" style="color: #163573; height: 30px; width: 30px;" />
						</button>
					</div>
					<slot name="header">
						Selecione o Grupo:
					</slot>
				</header>

				<div class="select">
					<section class="body">
						<select name="grupo" v-model="id_group">
							<option :value="item.id" v-for="(item, index) in groups" :key="index">
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
			<div class='row' v-for="(item, index) in points" :key="index">
				<div class="points">
					<div class="box little-box">{{ item.order }}º</div>
					<div class="box little-box">{{ item.teamName }}</div>
					<div class="box points-box">{{ item.points }}pts</div>
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
import axios from 'axios';

export default {
	props: ["id_modality"],
	components: {
	},
	name: "points-group-site",
	data() {
		return {
			id_group: null,
			groups: [],
			points: [],
		};
	},
	methods: {
		async pesquisar() {
			let res = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/points-per-group?groupId=' + this.id_group + '&modalityId=' + this.id_modality);
			this.points = res.data;
		},
		voltar() {
			location.reload();
		},
	},
	async mounted() {
		let response = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/groups?modalityId=' + this.id_modality);
		this.groups = response.data;
		this.id_group = this.groups[0].id;

		let res = await axios.get('https://apcefbaapias.azurewebsites.net/v1/web-app/points-per-group?groupId=' + this.id_group + '&modalityId=' + this.id_modality);
		this.points = res.data;
	}
}
</script>

<style scoped>
#pointsgroup {
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
	width: 45vw;
	border: 1px solid #163573;
	margin-top: 5%;
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
	margin-bottom: 100px;
	justify-content: flex-start;
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

.points {
	display: flex;
	align-items: center;
	justify-content: flex-start;
	width: 90%;
	margin-left: 1%;
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

.points-box {
	height: 4vh;
	width: 10%;
	border-radius: 5%;
	display: flex;
	justify-content: flex-end;
	padding: 10px;
}

.little-box {
	height: 4vh;
	border-radius: 10%;
	width: 7%;
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
	#pointsgroup {
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

	.points-box {
		width: 20%;
	}

	.points {
		gap: 1rem;
		margin-left: 0%;
	}

	hr {
		width: 90vw;
	}

	.search {
		width: 10%;
		height: 25%;
	}
}
</style>