<template>
  <b-card>
    <h2>Using only props</h2>
    <b-card-text>
      If we don't need to modify the async props
      on the child component, using props normally works.
      The template will be updated when the parent component
      receives the props.
    </b-card-text>
    <template v-slot:footer>Props works: {{msg}}</template>
  </b-card>
</template>

<script>
export default {
  props: {
    msg: String
  }
};
</script>
