<template>
  <div id="app">
    <ul>
      <li><a href="#home">主页面</a></li>
      <li><a href="#news">流量分析</a></li>
      <li><a href="#contact">入侵动作</a></li>
      <li><a href="#about">原始告警信息</a></li>
      <li><a href="#search">查找</a></li>
    </ul>
    <Data/>
    <Network/>
  </div>
</template>

<script>
import Network from './components/Network'
import Data from "./components/Data"

export default {
  name: 'App',
  components: {
    Network,
    Data
  }
}
</script>

<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

li {
  float: left;
}

a:link, a:visited {
  display: block;
  width: 140px;
  font-weight: bold;
  color: #FFFFFF;
  background-color: #bebebe;
  text-align: center;
  padding: 15px;
  text-decoration: none;
  text-transform: uppercase;
}

a:hover, a:active {
  background-color: #e6e6e6;
}
</style>
