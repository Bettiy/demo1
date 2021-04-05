<template>
  <button @click="num--">-</button>
  <input type="text" size="2" v-model="num">
  <button @click="num++">+</button>

  <br>

  <button @click="sub">-</button>
  <input type="text" size="2" v-model="num">
  <button @click="add">+</button>

  <br>

  <button @click="sub('hello')">-</button>
  <input type="text" size="2" v-model="num">
  <button @click="add($event)">+</button>

  <!--  <br>
    <div id="box1" @click="one">
      <div id="box2" @click.stop="two">
        <button @click.stop="three">按钮</button>
      </div>
    </div>-->
  <!--  <br>
    <div id="box1" @click="one">
      <div id="box2" @click.self.stop="two">
        <button @click="three">按钮</button>
      </div>
    </div>-->
  <br>
  <div id="box1" @click.capture="one">
    <div id="box2" @click.capture="two">
      <button @click="three">按钮</button>
    </div>
  </div>
  <br>
  <a href="https://www.baidu.com" @click.prevent="demo" style="text-decoration: none">百度一下</a>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      num: 0
    }
  },
  methods: {
    sub(a) {
      console.log(a);
      this.num--;
    },
    add(event) {
      console.log(event);
      this.num++;
    },
    one() {
      console.log('1111111111');
    },
    two() {
      console.log('2222222222222');
    },
    three() {
      console.log('333333333');
    },
    demo() {
      console.log('阻止事件默认行为');
    }
  }
}
</script>

<style scoped>
#box1 {
  width: 300px;
  height: 300px;
  background: red;
}

#box2 {
  width: 150px;
  height: 150px;
  background: green;
}
</style>