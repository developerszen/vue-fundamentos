<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Ciclo de vida en Vue
        </v-col>

        <v-col cols="12">
            <v-btn color="error" @click="show_component = !show_component">
                Ocultar componente
            </v-btn>
            <class-component v-if="show_component"></class-component>
        </v-col>
    </v-row>
</template>

<script>
import ClassComponent from "@/components/09-component.vue";

export default {
    components: {
        ClassComponent,
    },
    data() {
        return {
            show_component: true,
        }
    }
}
</script>