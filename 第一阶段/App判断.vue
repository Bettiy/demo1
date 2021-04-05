<template>
<!--  <button @click="isShow = !isShow">显示/隐藏</button>
  <div v-if="isShow">
    {{ msg }}
  </div>

  <div v-show="isShow">
    {{ msg }}
  </div>-->

<!--  <button @click="isShow = !isShow">显示/隐藏</button>
  <div v-if="isShow">
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
  </div>
  <div v-else>
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
  </div>-->


  <button @click="card = 1">按钮1</button>
  <button @click="card = 2">按钮2</button>
  <button @click="card = 3">按钮3</button>
  <button @click="card = 4">按钮4</button>
  <div v-if="card === 1">
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
    1111111111111111111111<br>
  </div>
  <div v-else-if="card === 2">
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
    2222222222222222222222<br>
  </div>
  <div v-else-if="card === 3">
    3333333333333333333333<br>
    3333333333333333333333<br>
    3333333333333333333333<br>
    3333333333333333333333<br>
    3333333333333333333333<br>
  </div>
  <div v-else>
    4444444444444444444444<br>
    4444444444444444444444<br>
    4444444444444444444444<br>
    4444444444444444444444<br>
    4444444444444444444444<br>
  </div>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: 'this is test',
      isShow: true,
      card: 1
    }
  },
}
</script>

<style scoped>

</style>