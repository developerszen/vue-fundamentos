<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Petición asíncrona
        </v-col>

        <v-col cols="12">
            <v-btn color="primary" @click="fetchData()">Cargar</v-btn>
            
            <v-alert v-if="loading" type="info">
                Cargando, espere por favor...
            </v-alert>

            <pre v-else>{{ posts }}</pre>
        </v-col>
    </v-row>
</template>

<script>
import axios from "axios";

export default {
    created() {
        this.fetchData();
    },
    data() {
        return {
            loading: false,
            posts: []
        }
    },
    methods: {
        fetchData() {
            this.loading = true; 

            axios.get("https://jsonplaceholder.typicode.com/posts")
            .then((response) => {
                this.loading = false;
                this.posts = response.data;
            });
        }
    }
}
</script>