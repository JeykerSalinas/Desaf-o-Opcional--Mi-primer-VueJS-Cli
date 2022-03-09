<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1>Tabla de usuarios</h1>
        </div>
      </div>
      <div class="row">
        <div class="col-12">
          <table class="table">
            <thead>
              <tr>
                <th scope="col">#</th>
                <th scope="col">Nombre</th>
                <th scope="col">Apellido Materno</th>
                <th scope="col">Apellido Paterno</th>
                <th scope="col">Edad</th>
                <th scope="col">Teléfono</th>
                <th scope="col">Dirección</th>
                <th scope="col">Correo</th>
                <th scope="col">Estado Civil</th>
              </tr>
            </thead>
            <tbody id="myTable">
              <tr v-for="(trabajador, i) in myData" :key="i">
                <td>{{ i + 1 }}</td>
                <td>{{ trabajador.nombre }}</td>
                <td>{{ trabajador.apellidoMaterno }}</td>
                <td>{{ trabajador.apellidoPaterno }}</td>
                <td>{{ trabajador.edad }}</td>
                <td>{{ trabajador.telefono }}</td>
                <td>{{ trabajador.direccion }}</td>
                <td>{{ trabajador.correo }}</td>
                <td>{{ trabajador.estadoCivil }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      myData: [],
    };
  },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      try {
        const URL = "./data.json";
        const request = await fetch(URL);
        const data = await request.json();
        this.myData = data;
        console.log(this.myData);
      } catch (error) {
        console.error(error);
      }
    },
  },
};
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
