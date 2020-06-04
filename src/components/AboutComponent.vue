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
    <span v-html="rawHtml"></span>
    <div class="buttons">
      <button v-on:click="showMessage">v-on:click example</button>
      <button @click="showMessage">@click example</button>
    </div>
    <div>
      <label>Insert text here:</label>
      <!-- v-model is used for 2-way data binding;
          key changing is the most efficient way to force re-render in Vue js 
      -->
      <input type="text" v-model="inputContent" />
      <p class="blue">
        <b>inputContent is</b>
        {{ inputContent }}
      </p>
    </div>
    <div class="rerender">
      <input :key="inputKey" type="text" value="Test the re-render!" />
      <button @click="forceRerender">Re-render the input!</button>
    </div>
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
      number: 10,
      inputKey: 0,
      inputContent: "First"
    };
  },
  methods: {
    showMessage() {
      alert("Hello!");
    },

    forceRerender() {
      console.log("rerender");
      this.inputKey += 1;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div,
p,
span {
  margin: 20px 0;
}
button {
  margin: 10px 0;
}

label {
  color: black;
}

.about-component {
  border: 1px solid black;
  display: inline-block;
  padding: 15px;
}

.buttons,
.rerender {
  display: inline-grid;
}

.blue {
  color: blue;
}
</style>
