<template>
  <div>
    <v-container>
      <v-row>
        <v-col md="4">
          <div id="visualization"></div>
        </v-col>
        <v-col md="8">
          <Table ref="child" ></Table>
        </v-col>
      </v-row>
    </v-container>



  </div>
</template>

<script>
import Table from './Table'
import {DataSet, Network} from '../../node_modules/vis-network/standalone/umd/vis-network.min'

export default {
  name: 'NetWork',
  components: {
    Table
  },
  data() {
    return {
      network: null
    }
  },
  mounted() {
    this.create();
  },
  methods: {
    create() {
      // create an array with nodes
      const nodes = new DataSet([
        {id: 1, label: "IP 1"},
        {id: 2, label: "IP 2"},
        {id: 3, label: "IP 3"},
        {id: 4, label: "IP 4"},
        {id: 5, label: "IP 5"},
      ]);

      // create an array with edges
      const edges = new DataSet([
        {from: 1, to: 3},
        {from: 1, to: 2},
        {from: 2, to: 4},
        {from: 2, to: 5},
      ]);

      // create a network
      const container = document.querySelector('#visualization');

      // provide the data in the vis format
      const data = {
        nodes: nodes,
        edges: edges
      };
      const options = {
        edges: {
          arrows: {
            to: true
          }
        }
      };
      // initialize your network!
      this.network = new Network(container, data, options);
      this.network.on("selectNode", this.$refs.child.clickOn);
      this.network.on("deselectNode", this.$refs.child.clickOff);
    }
  }
}
</script>
<style scoped>
#visualization {
  width: 400px;
  height: 400px;
  border: 1px solid lightgray;
}
</style>
