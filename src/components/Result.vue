<script setup>
    const props = defineProps(['selectOpera', 'funcSoma', 'funcSub', 'funcMult', 'funcDivisao'])
</script>
<template>
    <div class="row col-md-2 text-center ms-1 fs-1">
        <div class="form-control  border-3 border-warning">
                <p class="m-0 p-2 fw-bold" v-if="props.selectOpera === 'soma'">{{ props.funcSoma }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.selectOpera === 'subtracao'">{{ props.funcSub }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.selectOpera === 'multiplicacao'">{{ props.funcMult }}</p>
                <p class="m-0 p-2 fw-bold" v-else>{{ props.funcDivisao }}</p>
        </div>
    </div>
</template>
