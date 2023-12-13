<script setup>
import { ref } from 'vue';


let parqueadero = ref([{
  tipo: 'moto',
  stay: true
},
{
  tipo: 'moto',
  stay: false
},
{
  tipo: 'moto',
  stay: true
},
{
  tipo:'carro',
  stay:true
},
{
  tipo:'carro',
  stay:true
},
{tipo:'carro',
  stay:true
}])

function changecolor(index){

parqueadero.value[index].stay = !(parqueadero.value[index].stay)

}

</script>

<template>

<div class="grid grid-cols-2 max-w-2xl"> 

<div v-for="(obj, index) in parqueadero" :key="index">
<div v-if="obj.tipo == 'moto'">
<div @click="changecolor(index)" class="bg-green-400 w-36 h-32 mt-4" v-if="obj.stay == true">{{ obj.stay }}</div>
<div @click="changecolor(index)" class="bg-red-400 w-36 h-32 mt-4" v-else>{{ obj.stay }}</div>
</div>
</div>

<div v-for="(obj, index) in parqueadero" :key="index">

<div v-if="obj.tipo =='carro'">
<div @click="changecolor(index)" class="bg-green-400 w-36 h-56 mt-4" v-if="obj.stay">{{ obj.stay }}</div>
<div @click="changecolor(index)" v-else class="bg-red-400 w-36 h-56 p-6">{{ obj.stay }}</div>
</div>

</div>

</div>

</template>


