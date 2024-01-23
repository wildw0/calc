<script setup>
const props = defineProps(['firstNumb', 'secondNumb', 'selectOpera']);
</script>
<template>
    <form>
        <div class="row">
            <div class="d-inline-flex">
                <input @change="props.firstNumb" required
                    type="number" placeholder="1º número" class="form-control text-center p-1  border-3 border-warning  p-2 me-1 fs-1">
                <div class="row col-md-2 ms-1 me-1">
                    <select @change="props.selectOpera" class="form-control border-3 border-warning text-center fs-1">
                        <option value="soma">+</option>
                        <option value="subtracao">-</option>
                        <option value="multiplicacao">x</option>
                        <option value="divisao">÷</option>
                    </select>
                </div>
                <input @change="props.secondNumb" required
                    type="number" placeholder="2º número" class="form-control text-center p-1  border-3 border-warning  p-2 ms-1 me-1 fs-1">
            </div>
        </div>
    </form>
</template>