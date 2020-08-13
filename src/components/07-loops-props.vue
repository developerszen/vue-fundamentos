<template>
    <v-list-item>
            <v-list-item-content>
              <v-list-item-title>
                <strong>{{ product.name }}</strong>
                ({{ product.buy ? 'Comprar' : 'Preguntar' }})
              </v-list-item-title>

              <v-list-item-subtitle>
                <strong>Precio:</strong>
                {{ product.price }}
              </v-list-item-subtitle>

              <v-list-item-subtitle>
                <strong>Cantidad:</strong>
                {{ product.count }}
              </v-list-item-subtitle>
            </v-list-item-content>

            <v-list-item-action>

              <v-list-item-action-text class="subtitle-1 black--text">
                <strong>Precio total:</strong>
                {{ getPrice() }}
              </v-list-item-action-text>

              <v-btn color="error" @click="deleteProduct()">Eliminar</v-btn>

            </v-list-item-action>

    </v-list-item>
</template>

<script>
export default {
    props: ['product', 'index'],
    methods: {
        getPrice() {
            return this.product.price * this.product.count;
        },
        deleteProduct() {
            this.$emit("deleteProductApp", this.index)
        },
    }
}
</script>