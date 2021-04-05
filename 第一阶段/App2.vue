<template>
  <h1>{{ msg + '' + str }}</h1>
  <h1>{{ num + num * 2 }}</h1>
  <h2>{{ num }}</h2>
  <h2 v-pre>{{ num }}</h2>
  <pre>
    aaa bbb
    ccc
  </pre>
  <button @click="num++">按钮</button>
  <h2 v-once>{{ num }}</h2>
  <h2 v-text="msg"></h2>
  <h2 v-text="num*10"></h2>
  <h2 v-html="url"></h2>
  <h2>你&nbsp;好</h2>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: 'hello vue',
      str: 'hello test',
      num: 100,
      url: '<a href="https://www.baidu.com" style="text-decoration: none">百度一下</a>'
    }
  },
}
</script>

<style scoped>

</style>