<template>
  <div id="app">
    <el-container>
      <el-header style="text-align: right; font-size:12px">
        <div>
          <el-menu  class="el-menu-demo" mode="horizontal" :router="true">
            <el-menu-item index="1" :route="{name: 'home'}">Home</el-menu-item>
            <el-submenu index="2">
              <template slot="title">Workspace</template>
              <el-menu-item :route="{name: 'page1' }" index="2-1">Page1</el-menu-item>
              <el-menu-item index="2-2">item two</el-menu-item>
              <el-menu-item index="2-3">item three</el-menu-item>
              <el-submenu index="2-4">
                <template slot="title">item four</template>
                <el-menu-item index="2-4-1">item one</el-menu-item>
                <el-menu-item index="2-4-2">item two</el-menu-item>
                <el-menu-item :route="{name: 'about'}" index="2-4-3">About</el-menu-item>
              </el-submenu>
            </el-submenu>
            <el-menu-item index="3" disabled>Info</el-menu-item>
            <el-menu-item index="4"><a href="https://www.ele.me" target="_blank">Orders</a></el-menu-item>
          </el-menu>
        </div>
      </el-header>
      <el-main>
        <span>{{ testVar }}</span>
          <ul>
            <li v-for="(testArr, index) in testArray" v-bind:key='index'>{{ ++index}} {{ testArr }}
            <span style="{color: '#f50000';}" v-if="testArr == 'Вика'">{{ girlsName }}</span>
            </li>
          </ul>
          <el-input placeholder="Please input" v-model="input"></el-input>
          <el-button @click="pushArray">Default</el-button>
       </el-main>
    </el-container>
       <router-view/>
  </div>
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      testVar: 'First independent variable',
      activeIndex: '1',
      testArray: [
        'first', 'second', 'third'
      ],
      products: [],
      input: "",
      girlsName: "!!!Вика detected!!!"
    }
  },
  methods: {
    handleSelect () {
          console.log('Handle select methed')
    },
    pushArray() {
      this.testArray.push(this.input);
     console.log(this.$route.path)
    }
  },
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
