<template>
    <div class="modal-backdrop">
        <div class="modal">
            <div>
                <header class="modal-header">
                    <slot name="header">
                        Selecione a modalidade:
                    </slot>
                </header>

                <section class="modal-body">
                    <select name="modalidade" v-model="id_modality" class="form-control">
                        <option :value="item.id" v-for="(item, index) in modalities" :key="index">
                            {{ item.name }}
                        </option>
                    </select>
                </section>
            </div>

            <button class="search" v-on:click="pesquisar"><font-awesome-icon icon="fa-solid fa-magnifying-glass" style="color: #ffffff;" class="icon" /></button>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'modal-site',
    data() {
        return {
            id_modality: "259561ee-734e-44dd-9567-08dba1eef486",
            modalities: {},
        }
    },
    methods: {
        close() {
            this.$emit('close');
        },
        pesquisar() {
            this.$emit('changed', this.id_modality);
        }
    },
    async mounted() {
        await axios
            .get('https://apcefbaapias.azurewebsites.net/v1/web-app/modalities')
            .then(response => (
                this.modalities = response.data
            ));
    },
};
</script>

<style scoped>
.modal-backdrop {
    position: fixed;
    top: 0%;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.3);
    display: flex;
    justify-content: center;
    align-items: flex-end;
    width: 50%;
    left: 25%;
}

.modal {
    background: #163573;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: center;
    padding-bottom: 10px;
    padding-top: 10px;
}

.modal-header {
    padding: 15px;
    display: flex;
    position: relative;
    color: white;
    justify-content: space-between;
    font-weight: bolder;
    font-size: x-large;
    width: 100%;
}

.modal-body {
    position: relative;
    padding: 15px;
    width: 100%;
}

select {
    width: 100%;
}

.search {
    background-color: green;
    border: none;
    color: white;
    padding: 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 20px;
    border-radius: 50%;
    height: 100%;
    cursor: pointer;
    margin: 20px;
}

@media (pointer:coarse) {
    .modal-backdrop {
        width: 100%;
        left: 0;
    }

    .search {
        margin-top: 9%;
    }
}
</style>