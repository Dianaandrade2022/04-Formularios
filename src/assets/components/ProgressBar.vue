<template>
<h3 class="text-center text-success" v-if ="porcentaje == 100">Progreso: {{porcentaje}}%</h3>
<h3 class="text-center text-info" v-else>Progreso: {{porcentaje}}%</h3>

            <div class="progress" v-if ="porcentaje == 100">
                <div class="progress-bar progress-bar-striped progress-bar-animated bg-success" 
                role="progressbar" 
                :aria-valuenow="porcentaje" 
                aria-valuemin="0"
                aria-valuemax="100"
                :style="`width: ${porcentaje}%`"> 
                </div>
            </div>

            <div class="progress" v-else>
                <div class="progress-bar progress-bar-striped progress-bar-animated bg-secondary" 
                role="progressbar" 
                :aria-valuenow="porcentaje" 
                aria-valuemin="0"
                aria-valuemax="100"
                :style="`width: ${porcentaje}%`">   
                </div>
            </div>
</template>

<script>
    export default{
        props: {
            porcentaje: Number,
        },
    };
</script>