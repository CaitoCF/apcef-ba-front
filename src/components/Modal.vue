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
export default {
    name: 'modal-site',
    data() {
        return {
            id_modality: null,
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
        this.modalities = [{ 'id': 1, 'name': 'Futebol' }];
    },
};
</script>

<style>
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
    /* flex-direction: column; */
    /* align-items: flex-start; */
    width: 100%;
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
    margin: 4px 2px;
    border-radius: 50%;
    height: 100%;
    margin-top: 4%;
    margin-left: 5%;
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