<template>
  <b-card>
    <h2>Using only props</h2>
    <b-card-text>
      Trying to use the value of an async prop
      in lifecycle hooks does not work.
      Use instead a computed or watch.
    </b-card-text>
    <template v-slot:footer>
      <div>Created: {{msgFromCreated}}</div>
      <div>Mounted: {{msgFromMounted}}</div>
      <div>Updated: {{msgFromUpdated}}</div>
    </template>
  </b-card>
</template>

<script>
export default {
  data() {
    return {
      msgFromCreated: "undefined",
      msgFromMounted: "undefined",
      msgFromUpdated: "undefined"
    };
  },
  props: {
    msg: String
  },
  created() {
    this.msgFromCreated = this.msg;
  },
  mounted() {
    this.msgFromMounted = this.msg;
  },
  updated() {
    this.msgFromUpdated = this.msg;
  }
};
</script>
