<script>
export default{
    data: ()  => ({
        proyecto: "",
        tipo: "",
        urgente: false,
        proyectos: [],
    }),
    methods: {
        registrarProyecto() {
            const proyecto = {
                proyecto: this.proyecto,
                tipo: this.tipo,
                urgente: this.urgente,
            };
            this.proyectos.push(proyecto);

            this.proyecto = "";
            this.tipo = "";
            this.urgente = false;
        },
    },        
};
</script>

<template>

    <form @submit="registrarProyecto"> 
        
        <div class="mb-3">
            
            <label class="form-label"> Proyecto</label>
            <input v-model="proyecto" type="text" class="form-control" required/>
        </div>

        <div class="mb-3">
            
            <label class="form-label">Actividad</label>
            <select class="form-selected" required>
                <option disabled selected value="">Selecciona un tipo de actividad</option>
                <option >Aplicaciones web con Vue.js</option>
                <option >Backend Services con Node.js</option>
                <option>App movil con React Native</option>
            </select>
        </div>

        <div class="mb-3">
            
            <label for="exampleInputPassword1" class="form-check-label"> Urgente </label>
            <input v-model="urgente" type="checkbox" class="form-check-input" />
        </div>

        <button type="submit" class="btn btn-primary">Guardar</button>

    </form>
    <hr>

    <div class="table-responsive">
        <table class="table table-dark">
            <thead>
                <th>#</th>
                <th>Proyectos</th>
                <th>Tipo</th>
                <th>Urgente</th>
            </thead>

            <tbody>
                <tr>
                    <td>1</td>
                    <td>Laravel app</td>
                    <td>Larabel</td>
                    <td class="bg-success">Si / No </td>
                </tr>
            </tbody>
        </table>
    </div>
    
    
</template>

