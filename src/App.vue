/* eslint-disable */
<template>
  <div id="app">
    <h1>Hello Vue.js !</h1>
    <HyperTree :config="config" :onChange="setHyperTreeLastAction"/>
    <div>
      Hypertree last action (please try to expand/collapse nodes): <strong>{{ hyperTreeLastAction }}</strong>
    </div>
  </div>
</template>

<script>
import HyperTree from "./components/HyperTree.vue";

export default {
  name: "app",
  components: {
    HyperTree
  },
  data: () => ({
    config: {
      title: "Hyper Tree Title",
      nodes: [
        {
          text: "Node1",
          children: [
            {
              text: "Node5"
            }
          ]
        },
        {
          text: "Node2",
          children: [
            {
              text: "Node6",
              children: [
                {
                  text: "Node10"
                }
              ]
            },
            {
              text: "Node7"
            }
          ]
        },
        {
          text: "Node3",
          children: [
            {
              text: "Node8"
            },
            {
              text: "Node9",
              children: [
                {
                  text: "Node11"
                },
                {
                  text: "Node12"
                },
                {
                  text: "Node13"
                }
              ]
            }
          ]
        },
        {
          text: "Node4"
        }
      ]
    },
    hyperTreeLastAction: ""
  }),
  methods: {
    setHyperTreeLastAction: function(actionName) {
      this.hyperTreeLastAction = actionName;
    }
  }
};
</script>

<style>
</style>
