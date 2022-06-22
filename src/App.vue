<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Personas</h1>
  <FormularioPersona/>
  <TablaPersonas :personas="personas" />
</template>

<script>
import TablaPersonas from '@/components/TablaPersonas.vue'
import FormularioPersona from './components/FormularioPersona.vue'

export default {
  name: 'App',
  components: {
    TablaPersonas,
    FormularioPersona
},
  data() {
    return {
      personas: [
        {
          id: 1,
          nombre: 'Jon',
          apellido: 'Nieve',
          email: 'jon@email.com',
        },
        {
          id: 2,
          nombre: 'Tyrion',
          apellido: 'Lannister',
          email: 'tyrion@email.com',
        },
        {
          id: 3,
          nombre: 'Daenerys',
          apellido: 'Targaryen',
          email: 'daenerys@email.com',
        },
      ],
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
