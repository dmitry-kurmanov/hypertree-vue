/* eslint-disable */
<template>
   <div class="hypertree-container"></div>
</template>

<script>
import { h } from "hyperapp";
import { render } from "./_hypertree.js";

export default {
  name: "HyperTree",
  props: {
    config: {
      type: Object
    },
    onChange: {
      type: Function
    }
  },
  mounted() {
    const config = this.config;
    const onChange = this.onChange;

    const hypertree = window.HyperTree.render(
      config,
      document.querySelector(".hypertree-container")
    );
    hypertree.subscribe(function(data) {
      onChange(data.actionName);
    });
  }
};
</script>

<style scoped>
</style>
