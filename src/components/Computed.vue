<template>
  <div>
    <template>
      <b-card>
        <h2>Using computed</h2>
        <b-card-text>
          If we want to modify our props before displaying them
          we can use a computed property. The computed property
          will automatically update when the parent component
          receives the props.
          <b-alert
            variant="danger"
            show
          >Remember to check for undefined or set a default value for the props</b-alert>
        </b-card-text>
        <template v-slot:footer>
          <div>Computed works: {{msgRocks}}</div>
        </template>
      </b-card>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  },
  computed: {
    msgRocks() {
      return this.msg + " Rocks!!";
    }
  }
};
</script>
