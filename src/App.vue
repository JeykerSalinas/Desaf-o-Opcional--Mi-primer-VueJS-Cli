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
                <th scope="col">Apellido</th>
                <th scope="col">RUN</th>
                <th scope="col">Nacimiento</th>
                <th scope="col">Edad</th>
              </tr>
            </thead>
            <tbody id="myTable"></tbody>
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
      myData: [
        {
          nombre: "José",
          apellido: "Perez",
          run: 123456 - 2,
          nacimiento: "12-04-67",
          edad: 52,
        },
        {
          nombre: "María",
          apellido: "Rodríguez",
          run: 65432 - 1,
          nacimiento: "30-11-90",
          edad: 29,
        },
        {
          nombre: "Manuel",
          apellido: "Patiño",
          run: 14223456 - 6,
          nacimiento: "02-12-59",
          edad: 60,
        },
      ],
    };
  },
  components: {},
  methods: {
    renderData() {
      const myTable = document.getElementById("myTable");
      this.myData.map((a) => {
        myTable.innerHTML += `<tr>
          <th scope="row">${this.myData.indexOf(a) + 1}</th>
          <td>${a.nombre}</td>
          <td>${a.apellido}</td>
          <td>${a.run}</td>
          <td>${a.nacimiento}</td>
          <td>${a.edad}</td>

        </tr>`;
      });
    },
  },
  mounted() {
    this.renderData();
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
