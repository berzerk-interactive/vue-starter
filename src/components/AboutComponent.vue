<template>
  <div class="about-component">
    <p>
      <b>Prop 'msg' of the AboutComponent:</b>
      {{ msg }}
    </p>
    <p>
      <b>Prop 'number' of the AboutComponent:</b>
      {{ number }}
    </p>
    <div class="buttons">
      <button v-on:click="showMessage">v-on:click example</button>
      <button @click="showMessage">@click example</button>
    </div>
    <span v-html="rawHtml"></span>
  </div>
</template>

<script>
export default {
  name: "AboutComponent",
  props: {
    msg: { type: String, default: "This is the default message." } // required: true
  },
  data() {
    return {
      rawHtml: '<p style="font-size:18px;color:red;">v-html is cool!</p>',
      number: 10
    };
  },
  methods: {
    showMessage() {
      alert("Hello!");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
p {
  margin: 30px 0;
}
button {
  margin: 10px 0;
}

.about-component {
  border: 1px solid black;
  display: inline-block;
  padding: 15px;
}

.buttons {
  display: inline-grid;
}
</style>
