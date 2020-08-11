<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Directivas condicionales
        </v-col>
        
        <v-col cols="12">
            <div v-show="form.name">
                <strong>El nombre del producto es:</strong>
                {{ form.name }}
            </div>

            <!-- Name -->
            <small v-show="!form.name" class="error--text">
                El campo nombre es obligatorio
            </small>

            <small v-show="form.name" class="success--text">Nombre válido!!</small>

            <v-text-field v-model="form.name" label="Nombre" outlined dense>
            </v-text-field>

            <!-- Price -->
            <small v-if="!form.price" class="error--text">
                El producto debe tener un precio
            </small>

            <small v-else class="success--text">
                Precio válido!!!
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
            <v-switch v-model="form.buy" label="Comprar producto" color="secondary">
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