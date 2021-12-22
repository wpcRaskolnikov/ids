<template>
  <div class="dataClass" v-show="showTable">
    <v-data-table
        :headers="headers"
        :items="items"
        class="elevation-1"
    ></v-data-table>
  </div>
</template>

<script>
export default {
  name: 'Table',
  data() {
    return {
      showTable: false,
      items: [{
        time: '2021.12.01',
        type: 'doc',
        srcIp: '127.01.01',
        dstIp: '127.02.02',
        srcPort: '23',
        dstPort: '102',
        protocol: 'tcp'
      }],
      headers: [
        {text: 'time', align: 'center', value: 'time',},
        {text: 'type', align: 'center', value: 'type'},
        {text: 'srcIp', align: 'center', value: 'srcIp'},
        {text: 'dstIp', align: 'center', value: 'dstIp'},
        {text: 'srcPort', align: 'center', value: 'srcPort'},
        {text: 'dstPort', align: 'center', value: 'dstPort'},],
    }
  },
  methods: {
    clickOn() {
      this.showTable = true
    },
    clickOff() {
      this.showTable = false
    },

  },
}
</script>

<style scoped>
.dataClass {
  margin: 100px 150px 100px 80px;
}
</style>
