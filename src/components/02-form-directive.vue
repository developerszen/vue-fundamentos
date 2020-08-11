<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Directiva v-model
        </v-col>
        
        <v-col cols="12">
            <div>
                <strong>El nombre del producto es:</strong>
                {{ form.name }}
            </div>
            <!-- Name -->
            <v-text-field v-model="form.name" label="Nombre" outlined dense>
            </v-text-field>

            <!-- Price -->
            <v-text-field type="number"
            v-model="form.price"
            label="Precio unitario"
            outlined dense>
            </v-text-field>

            <!-- Count -->
            <v-text-field type="number"
            v-model="form.count"
            label="Cantidad"
            outlined dense>
            </v-text-field>

            <!-- Buy -->
            <v-switch v-model="form.buy" label="Comprar producto" color="secondary">
            </v-switch>

            <pre>
                {{ $data }}
            </pre>
        </v-col>
    </v-row>
</template>

<script>
export default {
    data() {
        return {
            form: {
                name: "Harina",
                price: 1,
                count: 1,
                buy: true
            },
        }
    }
}
</script>