<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld :msg="testData"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
//First commit 29102019 17:20
//Second commit without push
//Third commit with push 29102019 17:24
export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data () {
    return {
      testData: 'TEST'
    }
  }
}
</script>
