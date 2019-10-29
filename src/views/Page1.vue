<template>
  <div class="home">

    <el-input
  placeholder="Please input (Page1) => Page1Component"
  v-model="prop2Data"
  clearable>
</el-input>
    <Page1Component :propData="prop2Data"/>

  </div>
</template>

<script>
// @ is an alias to /src
import Page1Component from '@/components/Page1Component.vue'

export default {
  name: 'page1',
  components: {
    Page1Component
  },
  data () {
    return {
      prop2Data: 'TEST for Page1Component'
    }
  }
}
</script>
