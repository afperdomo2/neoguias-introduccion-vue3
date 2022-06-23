<template>
  <div id="tabla-personas">
    <table class="table">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Email</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="persona in personas" :key="persona.id">
          <td>{{ persona.nombre}}</td>
          <td>{{ persona.apellido }}</td>
          <td>{{ persona.email}}</td>
          <td>
              <button class="btn btn-danger" @click="$emit('delete-persona', persona.id)">
                🗑️ Eliminar
              </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'tabla-personas',
    props: {
        personas: Array,
    },
  }
</script>

<style scoped></style>