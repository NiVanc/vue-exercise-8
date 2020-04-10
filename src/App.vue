<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <br />
        <button class="btn btn-primary" @click="activeComponent = 'appBlue'">Load Blue Template</button>
        <button class="btn btn-success" @click="activeComponent = 'appGreen'">Load Green Template</button>
        <button class="btn btn-danger" @click="activeComponent = 'appRed'">Load Red Template</button>
        <hr />
        <component :is="activeComponent">
          <h3 slot="blue">Welcome to the blue world!</h3>
          <h3 slot="green">Welcome to the green world!</h3>
          <h3 slot="red">Welcome to the red world!</h3>
        </component>
      </div>
    </div>
  </div>
</template>

<script>
import Blue from "./components/Blue.vue";
import Green from "./components/Green.vue";
import Red from "./components/Red.vue";

export default {
  data() {
    return {
      activeComponent: "appBlue"
    };
  },
  components: {
    appBlue: Blue,
    appGreen: Green,
    appRed: Red
  }
};
</script>

<style scoped>
h3 {
  font-style: italic;
}
</style>
