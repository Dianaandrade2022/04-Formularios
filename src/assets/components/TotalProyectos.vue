<template>
    <div class="row my-3">
    <div class="col-6">
            <h3 class="text-center">Total de proyectos : {{numeroProyectos}}</h3>
        </div>
        <div class="col-6 text-end">
            <button @click="limpiarData()" class="btn btn-light mb-2">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="19" fill="currentColor" class="bi bi-trash3-fill" viewBox="0 0 16 16">
                    <path d="M11 1.5v1h3.5a.5.5 0 0 1 0 1h-.538l-.853 10.66A2 2 0 0 1 11.115 16h-6.23a2 2 0 0 1-1.994-1.84L2.038 3.5H1.5a.5.5 0 0 1 0-1H5v-1A1.5 1.5 0 0 1 6.5 0h3A1.5 1.5 0 0 1 11 1.5Zm-5 0v1h4v-1a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0-.5.5ZM4.5 5.029l.5 8.5a.5.5 0 1 0 .998-.06l-.5-8.5a.5.5 0 1 0-.998.06Zm6.53-.528a.5.5 0 0 0-.528.47l-.5 8.5a.5.5 0 0 0 .998.058l.5-8.5a.5.5 0 0 0-.47-.528ZM8 4.5a.5.5 0 0 0-.5.5v8.5a.5.5 0 0 0 1 0V5a.5.5 0 0 0-.5-.5Z"/>
                </svg>
            </button>
        </div>
    
    <div class="table-responsive">
        <table class="table table-dark">  
            <thead class="text-center">
                <tr>
                    <th>#</th>
                    <th>Proyecto</th>
                    <th>Tipo</th>
                    <th>Urgente</th>
                    <th>Completado</th>
                </tr>
            </thead>

            <tbody class="table-light">
                <tr v-for="(proyecto,index) in proyectos" :key="index">
                    <th>{{index + 1}}</th>
                    <td>{{proyecto.proyecto}}</td>
                    <td>{{proyecto.tipo}}</td>
                    <td @click="cambiarEstado(proyecto,'urgente')"
                        :class="proyecto.urgente ? 'table-danger text-danger' : 'table-success text-success'" role="alert">{{proyecto.urgente ? "Si" : "No"}}</td>
                        <td @click="cambiarEstado(proyecto,'completado')"
                        :class="proyecto.completado ? 'table-success text-success' : 'table-danger text-danger'" role="alert">{{proyecto.completado ? "Completado" : "Incompleto"}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</div>
</template>

<script>
    export default {
        props: ['numeroProyectos',
        'proyectos',
        'cambiarEstado',
        'limpiarData',
    ],
        
    };
</script>