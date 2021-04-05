<template>
  <!--  <input type="text" v-model="msg" @input="inChange">
    <br>
    {{ msg }}-->

  <!--  <input type="text" v-model.lazy="msg">-->
  <!--  <input type="text" v-model.number.lazy.trim="msg">
    <br>
    {{ typeof (msg) }}
    <br>
    {{ msg }}-->

  <!--  <input id="one" type="radio" checked name="sex" v-model="sex" value="1" >男
    <input id="two" type="radio" name="sex" v-model="sex" value="2" >女
    <br>
    {{sex}}-->

  <input id="a" type="checkbox" v-model="isAgree">同意协议 {{ isAgree }}
  <br>
  <input id="b" type="checkbox" value="Java" v-model="tags">Java
  <input id="c" type="checkbox" value="PHP" v-model="tags">PHP
  <input id="d" type="checkbox" value="C" v-model="tags">C
  <input id="e" type="checkbox" value="Python" v-model="tags">Python
  {{ tags }}

  <br>
  <select v-model="language">
    <option value="java">Java</option>
    <option value="php">PHP</option>
    <option value="python">Python</option>
    <option value="c">C</option>
  </select>
  {{ language }}

  <br>
  <br>
  <select v-model="languages" multiple size="1">
    <option value="java">Java</option>
    <option value="php">PHP</option>
    <option value="python">Python</option>
    <option value="c">C</option>
  </select>
  {{ languages }}
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: 'this is test',
      sex: '',
      isAgree: false,
      tags: [],
      language: 'java',
      languages: [],
    }
  },
  methods: {
    inChange(event) {
      this.msg = event.target.value
    }
  }
}
</script>

<style scoped>

</style>