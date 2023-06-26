<script setup>
import {ref} from 'vue'
const props = defineProps(
    {
        name:{
            type:String,
            default:'No name'
        },
        index:{
            type:Number,
        }
    }
)

const borrar=(index)=>{
    emit('chao',index)
}

const duplicar=(name)=>{

    emit('duplicar',name)
}

const emit = defineEmits(['chao','duplicar'])

var numero=ref('')
var numero2=ref('')


const sumador1=()=>{

    numero.value++
}

const sumador2=()=>{

    numero2.value++
}


</script>

<template>

    <div class=" w-40 h-40 mx-10 items-center justify-center">
        <img src="../img/wolf-647528.jpg" alt="">
        <h1 class=" text-center font-bold">{{ props.name }}</h1>
        <div class=" flex">
            <img @click="sumador1" class=" w-10 h-10 mx-5" src="../img/me-gusta.png" alt="">
            <h1>{{ numero }}</h1>
            <h2 v-if="numero>5">Hola megusta</h2>
            <img @click=" sumador2" class=" w-10 h-10 mx-5" src="../img/disgusto.png" alt="">
            <h1>{{ numero2 }}</h1>
            <h2 v-if="numero2>5">Hola megusta</h2>
        </div>
    </div>
    <div>
        <button @click="borrar(props.index)" class=" bg-red-500 rounded-lg w-10 h-10 mb-2">X</button>
        <br>
        <button @click="duplicar(props.name)" class=" bg-red-500 rounded-lg w-10 h-10">D</button>
    </div>

    <h1>el resultado es multiplicacion,{{ numero*numero2 }}</h1>
    
</template>
