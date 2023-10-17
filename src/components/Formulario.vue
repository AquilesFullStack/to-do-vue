<script setup>
const props = defineProps(['valorInput1', 'valorInput2', 'filtro', 'selecioneFiltro'])
</script>

<template>
    <form>
        <div class="row mt-3">
            <div class="col-md-4">
                <input @keyup="props.valorInput1" class="form-control" placeholder="Insira o primeiro valor" type="number">
            </div>
            <div class="col-md-1" texte center>
                <p class="fs-4 m-0" v-if="props.filtro ==='soma'">+</p>
                <p class="fs-4 m-0" v-else-if="props.filtro === 'sub'">-</p>
                <p class="fs-4 m-0" v-else-if="props.filtro === 'mult'">x</p>
                <p class="fs-4 m-0" v-else="props.filtro === 'div'">/</p>
            </div>
            <div class="col-md-4 p-0">
                <input @keyup="props.valorInput2" class="form-control" placeholder="Insira o segundo valor" type="number">
            </div>
            <div class="col-md-3">
                <select @change="props.selecioneFiltro" class="form-control">
                <option value="soma">Soma</option>
                <option value="sub">Subtração</option>
                <option value="mult">Multiplicação</option>
                <option value="div">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>