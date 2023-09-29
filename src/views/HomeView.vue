<script setup>
import CommonForm from '../components/common/CommonForm.vue'
const personalFields = [
  {
    name: 'Nombres',
    type: 'text',
    options: null
  },
  {
    name: 'Apellidos',
    type: 'text',
    options: null
  },
  {
    name: 'Fecha de Nacimiento',
    type: 'text',
    options: null
  },
  {
    name: 'Centros de Estudio',
    type: 'select',
    options: [1,2,3,4]
  },
  {
    name: 'Grados',
    type: 'select',
    options: ['1ero']
  },
  {
    name: 'Sabes Nadar',
    type: 'select',
    options: ['Si', 'No']
  },
  {
    name: 'Sabes Flotar',
    type: 'select',
    options: ['Si', 'No']
  }
]
</script>

<template>
  <main>
    <CommonForm title="Informacion Personal" :fields="personalFields" />
  </main>
</template>
