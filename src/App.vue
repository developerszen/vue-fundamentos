<template>
  <v-app>
    <v-container>
      
      <class-interpolations></class-interpolations>
      <class-form-directive></class-form-directive>
      <class-directive-conditional></class-directive-conditional>
      <class-bind-directive></class-bind-directive>
    </v-container>
  </v-app>
</template>

<script>
import ClassInterpolations from "@/components/01-interpolations.vue";
import ClassFormDirective from "@/components/02-form-directive.vue";
import ClassDirectiveConditional from "@/components/03-conditional-directive.vue";
import ClassBindDirective from "@/components/04-bind-directive.vue";

export default {
  components: {
    ClassInterpolations,
    ClassFormDirective,
    ClassDirectiveConditional,
    ClassBindDirective
  }
}
</script>
