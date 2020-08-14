<template>
    <v-row>
        <v-col cols="12">
            <v-card>
                <v-card-title>Componente</v-card-title>
                <v-card-text>
                    <v-text-field label="Componente" v-model="component">
                    </v-text-field>
                </v-card-text>
            </v-card>
        </v-col>
    </v-row>
</template>

<script>
export default {
    beforeCreate() {
            console.log('Componente a punto de ser creado');        
    },
    created() {
            console.log('Componente creado');
    },
    beforeMount() {
            console.log('Componente a punto de ser agregado al DOM');
    },
    mounted() {
            console.log('Componente agregado al DOM');
    },
    beforeUpdate() {
            console.log("Los datos cambiaron y estan a punto de ser reflejados en el DOM");
    },
    updated() {
            console.log('Los datos cambiaron y fueron reflejados en el DOM');
    },
    beforeDestroy() {
            console.log('Componente a punto de ser destruido');
    },
    destroyed() {
            console.log('Componente destruido');
    },
    data() {
        return {
            component: ""
        }
    }
}
</script>