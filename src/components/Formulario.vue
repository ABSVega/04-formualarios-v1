<script>
export default{
    data: ()=> ({
        proyecto: "",
        tipo: "",
        urgente: false,
        proyectos: [],
    }),
    methods:{
        registrarProyecto(){
            const proyecto ={
                proyecto: this.proyecto,
                tipo: this.tipo,
                urgente: this.urgente,
            };
            this.proyectos.push(proyecto);

            this.proyecto ="";
            this.tipo = "";
            this.urgente = false;
        },
    },
};
</script>

<template>
  <form @submit.prevent="registrarProyecto">
    <div class="mb-3">
      <label class="form-label"> Proyecto </label>
      <input v-model.trim="proyecto" type="text" class="form-control" required />
    </div>

    <div class="mb-3">
      <label class="form-label">Actividades</label>
      <select v-model.trim="tipo" class="form-select" required>
        <option disabled selected value="">
          Seleciona un tipo de actividad
        </option>
        <option>Aplicaciones Web con Vue.js</option>
        <option>Backend Services con Node.js</option>
        <option>App movil con React Native</option>
      </select>
    </div>

    <div class="mb-3">
      <label for="exmapleInputPassword1" class="form-check-label">Urgente </label>
      <input v-model= "urgente" type="checkbox" class="form-check-input"/>
    </div>
    <button class="btn btn-success btn-block" type="submit">Enviar</button>
  </form>
  <hr>

  <div class="table-responsive">
    <table class="table table-dark">
        <thead>
            <tr>
                <th>#</th>
                <th>Proyecto</th>
                <th>Tipo</th>
                <th>Urgente</th>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td>1</td>
                <td>Laravel app</td>
                <td>Laravel</td>
                <td class="bg-success">Si/No</td>
            </tr>
        </tbody>
    </table>
  </div>
</template>
