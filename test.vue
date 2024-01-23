<script setup> 
import { reactive } from 'vue'; 
import Header1 from './components/Header1.vue'; 
import Form1 from './components/Form1.vue';
import Result from './components/Result.vue'; 

const state = reactive({ filtro: '', num1: '', num2: '', resultado: '', });

const setNum1 = (event) => { state.num1 = Number(event.target.value); }; 
const setNum2 = (event) => { state.num2 = Number(event.target.value); }; 
const setOpera = (event) => { state.filtro = event.target.value; };

const soma = () => { const resultadoSoma = state.num1 + state.num2; state.resultado = resultadoSoma; };

const subtracao = () => { const resultadoSubtracao = state.num1 - state.num2; state.resultado = resultadoSubtracao; };

const multiplicacao = () => { const resultadoMultiplicacao = state.num1 * state.num2; state.resultado = resultadoMultiplicacao; };

const divisao = () => { const resultadoDivisao = state.num1 / state.num2; state.resultado = resultadoDivisao; };

</script> <template> <div class="container"> 
    <Header1 /> 
    <div class="row"> <div class="d-inline-flex"> 
    <Form1 :firstNumb="setNum1" :secondNumb="setNum2" :selectOpera="setOpera" />
    <Result :selectOpera="state.filtro" :funcSoma="soma" :funcSub="subtracao" :funcMult="multiplicacao" :funcDivisao="divisao" /> 
    </div> </div> </div> </template> <style scoped></style> 
    
    <script setup> const props = defineProps(['firstNumb', 'secondNumb', 'selectOpera']); </script> 
    <template> 
    
    <form @submit.prevent="props.cadastraTarefa"> 
    <div class="row"> <div class="d-inline-flex"> 
        <input @change="props.firstNumb" required type="number" placeholder="1º número" class="form-control text-center p-1 border-3 border-warning p-2 me-1 fs-1"> 
        <div class="row col-md-2 ms-1 me-1"> 
            <select @change="props.selectOpera" class="form-control border-3 border-warning text-center fs-1"> 
            <option value="soma">+</option> 
            <option value="subtracao">-</option> 
            <option value="multiplicacao">x</option> 
            <option value="divisao">÷</option> 
            </select> 
            </div> 
            <input @change="props.secondNumb" required type="number" placeholder="2º número" class="form-control text-center p-1 border-3 border-warning p-2 ms-1 me-1 fs-1"> 
            </div> </div> 
            </form> </template> 
            
            <script setup> 
            const props = defineProps(['selectOpera', 'funcSoma', 'funcSub', 'funcMult', 'funcDivisao']) 
            </script> 
            <template> <div class="row col-md-2 text-center ms-1 fs-1"> 
                <div class="form-control border-3 border-warning"> 
                    <p class="m-0 p-2 fw-bold" v-if="props.selectOpera === 'soma'">{{ props.funcSoma() }}</p> 
                    <p class="m-0 p-2 fw-bold" v-else-if="props.selectOpera === 'subtracao'">{{ props.funcSub() }}</p> 
                    <p class="m-0 p-2 fw-bold" v-else-if="props.selectOpera === 'multiplicacao'">{{ props.funcMult() }}</p> 
                    <p class="m-0 p-2 fw-bold" v-else>{{ props.funcDivisao() }}</p> </div> </div> </template>