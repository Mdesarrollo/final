<script setup>
import {ref} from 'vue'
import cartasFinal from '@/components/cartasFinal.vue'

const usuarios=ref([
  {
    name:'maicol robles'
  },
  {
    name:'Maria sanchez'
  },
  {
    name:'Carlos Contreras'
  },
  {
    name:'Sergio perez'
  }
])

const borrar=(index)=>{

  usuarios.value.splice(index,1)

}

const duplicar=(name)=>{
  
  const n={
    name:name
  }

  usuarios.value.push(n)
}

var nombre

const agregar =()=>{

  const n2={
    name:nombre
  }

  usuarios.value.push(n2)
}

var titulo=ref('')

</script>

<template>
  <h1>{{ titulo }}</h1>
  <input class=" border border-black" type="text" v-model="nombre" placeholder="Agregar">
  <button @click="agregar" class=" bg-red-500 rounded-lg w-20 h-10">Agregar</button>
  <div class=" flex">
    <cartasFinal v-for="(user,index) in usuarios" :key="index" :name="user.name" :index="index" @chao="borrar" @duplicar="duplicar"></cartasFinal>
  </div>
  <input class=" border border-black" type="text" v-model="titulo" placeholder="Titulo">
</template>

