<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Personas</h1>
  <FormularioPersona @add-persona="agregarPersona" />
  <TablaPersonas
    :personas="personas"
    @delete-persona="eliminarPersona"
    @update-persona="actualizarPersona"
  />
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
  },
  methods: {
    agregarPersona(persona) {
      let id = 0;
      if (this.personas.length > 0) {
        id = this.personas[this.personas.length - 1].id + 1;
      }
      this.personas = [...this.personas, { ...persona, id}];
    },
    eliminarPersona(id) {
      this.personas = this.personas.filter(
        persona => persona.id !== id
      );
    },
    actualizarPersona(id, personaActualizada) {
      this.personas = this.personas.map(persona =>
        persona.id === id ? personaActualizada : persona
      )
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
