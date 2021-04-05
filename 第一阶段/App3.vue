<template>
  <!--  {{ msg }}
    <h2 title="this is a test">{{ msg }}</h2>
    <h2 :title="msg">hh</h2>
    <img :src="imgSrc" :width="size" :height="size" alt="">
    <br>

    <div :style="[fontSize, bgColor]">box</div>-->
  <div class="one two">box11111</div>
  <div :class="[one, two]">box22222</div>
  <div :class="active">box33333</div>
  <div :class="{one: isOne, two: isTwo}">box44444</div>
  <button @click="isOne = !isOne">button</button>
  <div :class="{demo}">box44444</div>
  <div class="" :class="getStyle">box66666</div>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: 'hello vue',
      imgSrc: 'https://v3.vuejs.org/logo.png',
      size: 100,
      fontSize: 'font-size: 100px',
      bgColor: 'background-color:green',
      one: 'one',
      two: 'two',
      active: ['two'],
      isOne: true,
      isTwo: true,
      demo: true,
    }
  },
  methods: {
    getStyle() {
      return [this.one, this.two];
    },
    /*getStyleObj() {
      return [this.one: this.isOne, this.two: this.isTwo]
    }*/
  }
}
</script>

<style scoped>
.one {
  background: red;
}

.two {
  font-size: 50px;
}

.demo {
  width: 100px;
  height: 100px;
  background: green;
}
</style>