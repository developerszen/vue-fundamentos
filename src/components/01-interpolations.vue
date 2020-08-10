<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Interpolaciones
        </v-col>

        <v-col cols="12">
            {{ name }}
        </v-col>
    </v-row>
</template>

<script>
export default {
    data() {
        return {
            name: "Harina"
        }
    }
}
</script>