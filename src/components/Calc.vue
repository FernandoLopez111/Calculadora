<template>
   <div class="h-screen bg-gray-300 flex justify-center py-16">
      <div class="w-1/3">
            <div class="p-4 text-right shadow-2xl rounded-t-lg bg-white">
                <input class="input px-2 py-4 border rounded text-end" type="text" v-model="resultado" disabled/>
            </div>
            <div class="grid grid-cols-4 grid-rows-5 shadow-2xl rounded-b-1g">
                <button class="p-6 text-white bg-gray-500 rounded col-span-2" @click="resultado= ''">AC</button>
                <button class="p-6 bg-gray-500 text-white rounded" @click="Del()">DEL</button>
                 <button class="p-6 bg-gray-500 text-white rounded" @click="Mod()">%</button>
                <button class="p-6 bg-gray-500 text-white rounded" @click="num('/')">÷</button>

                <button class="p-6 bg-blue-500 text-white rounded" @click="num('7')">7</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('8')">8</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('9')">9</button>                
                <button class="p-6 bg-gray-500 text-white rounded" @click="num('*')">x</button>

                <button class="p-6 bg-blue-500 text-white rounded" @click="num('4')">4</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('5')">5</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('6')">6</button>
                <button class="p-6 bg-gray-500 text-white rounded" @click="num('+')">+</button>

                <button class="p-6 bg-blue-500 text-white rounded" @click="num('1')">1</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('2')">2</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('3')">3</button>
                <button class="p-6 bg-gray-500 text-white rounded" @click="num('-')">-</button>

                <button class="p-6 bg-blue-500 text-white rounded" @click="num('0')">0</button>
                <button class="p-6 bg-blue-500 text-white rounded" @click="num('.')">.</button>
                <button class="p-6 bg-red-500 text-white rounded" @click="Calcular()">=</button>
            </div>
      </div>     
    </div>
</template>
<style>
.button{
  border: 1x solid;
}
</style>
<script lang="ts" setup>
import { ref } from 'vue';

const resultado = ref('')

const num =(numeros: string)=>{
  resultado.value += numeros
}

const Calcular = () =>{
  try{
  resultado.value = eval(resultado.value)
  }
  catch(error){
  resultado.value = ('Error')
  }
}
const Mod = () =>{
  try {
    let  result = eval(resultado.value)
    resultado.value = (result/100).toString();
  } catch (error) {
    
  }
}

const Del =()=>{
  resultado.value = resultado.value.slice(0,-1)
}

</script>

