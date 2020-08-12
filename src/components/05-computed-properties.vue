<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Propiedades calculadas
        </v-col>
        
        <v-col cols="12">
            <div v-show="form.name">
                <strong>El nombre del producto es:</strong>
                {{ form.name }}
            </div>

            <!-- Name -->
            <small v-bind:class="form.name ? 'success--text' : 'error--text'">
                {{ form.name ? 'Nombre válido!!!' : 'El campo nombre es obligatorio' }}
            </small>

            <v-text-field v-model="form.name" label="Nombre" outlined dense>
            </v-text-field>

            <!-- Price -->
            <small v-bind:class="{ 'success--text': form.price, 'error--text': !form.price }">
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

            <h2>
                <strong>Precio total:</strong>
                {{ totalPrice }}
            </h2>
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
    },
    computed: {
        totalPrice() {
            return this.form.price * this.form.count;
        }
    }
}
</script>