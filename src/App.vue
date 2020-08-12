<template>
  <v-app>
    <v-container>
      
      <class-interpolations></class-interpolations>
      <class-form-directive></class-form-directive>
      <class-directive-conditional></class-directive-conditional>
      <class-bind-directive></class-bind-directive>
      <class-computed-properties></class-computed-properties>

      <class-methods-events v-on:addProductApp="addProduct">
      </class-methods-events>

      <!-- List Products -->
      <v-row>
        <v-col cols="12">
          <h5>Lista de productos</h5>
        </v-col>

        <v-list three-line>


          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>
                <strong>Harina</strong>
                Producto 1
              </v-list-item-title>

              <v-list-item-subtitle>
                <strong>Precio:</strong>
                12
              </v-list-item-subtitle>

              <v-list-item-subtitle>
                <strong>Cantidad:</strong>
                18
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>


        </v-list>

      </v-row>

    </v-container>
  </v-app>
</template>

<script>
import ClassInterpolations from "@/components/01-interpolations.vue";
import ClassFormDirective from "@/components/02-form-directive.vue";
import ClassDirectiveConditional from "@/components/03-conditional-directive.vue";
import ClassBindDirective from "@/components/04-bind-directive.vue";
import ClassComputedProperties from "@/components/05-computed-properties.vue";
import ClassMethodsEvents from "@/components/06-methods-events.vue";

export default {
  components: {
    ClassInterpolations,
    ClassFormDirective,
    ClassDirectiveConditional,
    ClassBindDirective,
    ClassComputedProperties,
    ClassMethodsEvents
  },
  data() {
    return {
      products: []
    }
  },
  methods: {
    addProduct(product) {
      const new_product = {
        name: product.name,
        price: product.price,
        count: product.count,
        buy: product.buy,
      };

      this.products.push(new_product);
    }
  }
}
</script>
