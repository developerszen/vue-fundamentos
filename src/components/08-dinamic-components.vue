<template>
    <v-row>
        <v-col class="primary secondary--text font-weight-black" cols="12">
            Componentes dinámicos
        </v-col>

        <v-col cols="12">
            <v-btn color="primary"
            class="mr-2"
            @click="setComponent('class-interpolations')"
            >
                Interpolaciones
            </v-btn>

            <v-btn color="secondary"
            class="mr-2"
            @click="setComponent('class-form-directive')"
            >
                Directivas
            </v-btn>

            <transition name="fade" mode="out-in">
                <component :is="component" class="mt-3"></component>
            </transition>

        </v-col>
    </v-row>
</template>

<script>
import ClassInterpolations from "@/components/01-interpolations.vue";
import ClassFormDirective from "@/components/02-form-directive.vue";

export default {
    components: {
        ClassInterpolations,
        ClassFormDirective,
    },
    data() {
        return {
            component: ""
        }
    },
    methods: {
        setComponent(component) {
            this.component = component;
        }
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