<script setup >
    const props = defineProps(['filtro','funcaoSoma','funcaoSub','funcaoMult','funcaoDiv'])
</script>

<template>
    <div class="row mt-5">
        <div class="col d-flex align-items-center justify-content-center">
            <p class="m-0">Resultado</p>
            <div class="border rounded">
                <p class="m-0 p-2 fw-bold" v-if="props.filtro === 'soma'">{{ props.funcaoSoma }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.filtro === 'sub'">{{ props.funcaoSub }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.filtro === 'mult'">{{ props.funcaoMult }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.filtro === 'div'">{{ funcaoDiv }}</p>
            </div>
        </div>
    </div>
</template>