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
          <h5 v-show="products.length">Lista de productos</h5>
          <v-alert v-show="!products.length" type="info">
            No cuentas con productos registrados
          </v-alert>
        </v-col>

        <v-btn v-show="products.length" color="info" @click="show_list = !show_list">
            {{ show_list ? 'Ocultar lista' : 'Ver lista' }}
        </v-btn>

        <transition name="fade" mode="out-in">
          <v-list v-show="show_list" three-line>
            <class-loops-props 
            v-for="(product, index) in products" :key="index"
            :product="product"
            :index="index"
            @deleteProductApp="deleteProduct"
            >
            </class-loops-props>
          </v-list>
        </transition>
      </v-row>

      <v-row>
        <v-col cols="12">
          <h2>
            <strong>Total:</strong>
            {{ getTotal }}
          </h2>
        </v-col>
      </v-row>

      <class-life-cycle></class-life-cycle>

      <class-dinamic-components></class-dinamic-components>

      <class-sync></class-sync>
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
import ClassLoopsProps from "@/components/07-loops-props.vue";
import ClassLifeCycle from "@/components/09-lifecycle";
import ClassSync from "@/components/10-async.vue";

export default {
  components: {
    ClassInterpolations,
    ClassFormDirective,
    ClassDirectiveConditional,
    ClassBindDirective,
    ClassComputedProperties,
    ClassMethodsEvents,
    ClassLoopsProps,
    ClassLifeCycle,
    ClassSync,
  },
  data() {
    return {
      products: [],
      show_list: true,
    }
  },
  computed: {
    getTotal() {
      let total = 0;
      this.products.forEach((product) => {
        total += product.price * product.count;
      });

      return total;
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
    },
    deleteProduct(index) {
      this.products.splice(index, 1);
    },
  }
}
</script>

<style scoped>
    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.5s;
    }

    .fade-enter,
    .fade-leave-to {
        opacity: 0;
    }
</style>
