<template>
  <div class="ep-detail" id="Table" v-show="showTable">

    <table>
      <tr>
        <th v-for="(value,name,index) in alert" :key="index">
          {{name}}
        </th>
      </tr>
      <tr>
        <td v-for="(value,name,index) in alert" :key="index">
          {{value}}
        </td>
        <td><a href="" target="_blank">查看</a></td>
      </tr>
    </table>

  </div>
</template>

<script>
export default {
  name: "Table",
  data() {
    return {
      showTable: false,
      alert: {
        time: '2021.12.01',
        type: 'doc',
        srcIp: '127.01.01',
        dstIp: '127.02.02',
        srcPort: '23',
        dstPort: '102',
        protocol: 'tcp'
      }
    }
  },
  methods:{
    clickOn() {
      this.showTable = true
    },
    clickOff(){
      this.showTable = false
    }
  }
}
</script>

<style scoped>

/*表格美化*/
table {
  position: absolute;
  width: 90%;
  background: #ccc;
  margin: 10px auto;
  border-collapse: collapse;
}

th, td {
  height: 25px;
  line-height: 25px;
  text-align: center;
  border: 1px solid #ccc;
}

th {
  background: #e8e9f3;
  font-weight: bold;
}

tr {
  background: #fff;
}

tr:hover {
  background: rgb(240, 239, 239);
}

td a {
  color: #06f;
  text-decoration: none;
}

td a:hover {
  color: #06f;
  text-decoration: underline;
  cursor: pointer;
}
</style>
