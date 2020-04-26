<template>
  <div>
    <template>
      <b-card>
        <h2>Using watch</h2>
        <b-card-text>
          If we want to modify our props before displaying them
          we can use a computed property. The computed property
          will automatically update when the parent component
          receives the props.
        </b-card-text>
        <template v-slot:footer>
          <div>Watch works: {{msgCopy}}</div>
          <div>
            Using the value of async prop
            in data does not work: {{msgCopyBreaks}}
          </div>
        </template>
      </b-card>
    </template>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msgCopy: undefined,
      msgCopyBreaks: this.msg
    };
  },
  props: {
    msg: String
  },
  watch: {
    msg: function() {
      console.log(this.msg);
      this.msgCopy = this.msg;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
