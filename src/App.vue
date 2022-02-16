<template>
  <div id="app">
    <div class="container">
      <h1>mi lista</h1>
    <form v-on:submit.prevent="agregarTarea">
      <p>Nombre: <input type="text" v-model="nombre" /></p>
      <button type="submit">Agregar Tarea</button>
    </form>

    <h2>Esta es mi lista de tareas .</h2>

    <ul v-for="(tarea, index) in tareas" :key="tarea">
      <li>{{ index }} - {{ tarea.nombre }}</li>
    </ul>
    </div>
  </div>
</template>

<script>
export default {
  el: "App",
 
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    agregarTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      });
    },
  },
};
</script>

<style>
#app{
  display: flex;
  justify-content: center;
}
</style>
