<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Directivas de enlace
        </v-col>
        
        <v-col cols="12">
            <div v-show="form.name">
                <strong>El nombre del producto es:</strong>
                {{ form.name }}
            </div>

            <!-- Name -->
            <small class="error--text">
                {{ form.name ? 'Nombre válido!!!' : 'El campo nombre es obligatorio' }}
            </small>

            <v-text-field v-model="form.name" label="Nombre" outlined dense>
            </v-text-field>

            <!-- Price -->
            <small class="error--text">
                {{ form.price ? 'Precio válido!!!' : 'El producto debe tener un precio' }}
            </small>

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
            <v-switch v-model="form.buy"
            v-bind:label="form.buy ? 'Comprar producto' : 'Solicitar más información'"
            v-bind:color="form.buy ? 'primary' : 'secondary'">
            </v-switch>
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