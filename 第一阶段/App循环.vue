<template>
  <!--  <ul>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>-->

  <!--  <ul>
      <li v-for="(item, index) in list" :key="item">{{ index+1 }} {{ item }}</li>
    </ul>-->

  <!--  <ul>
      <li v-for="(item, key, index) in obj" :key="item.name">{{ index }}-{{key}} : {{ item }}</li>
    </ul>-->

  <button @click="add">添加</button>
  <input type="text" v-model="name">
  <ul>
    <li :class="{active:item.active}" @mouseenter="over(index)" @mouseout="out(index, item.name)"
        v-for="(item, index) in books"
        :key="item.id"><input type="checkbox">
      {{ index + 1 }} :
      {{ item.name }} ￥{{ item.price }}
    </li>
  </ul>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      list: ['java', 'python', 'PHP', 'Vue', 'React'],
      obj: {
        name: '学习乐园',
        url: 'https://www.baidu.com',
        text: '虚心使人落后'
      },
      newId: 6,
      name: '',
      books: [
        {id: 1, name: 'Java编程思想', price: 123, active: false},
        {id: 2, name: 'mysql编写思想', price: 425, active: false},
        {id: 3, name: 'PHP编程思想', price: 421, active: false},
        {id: 4, name: 'Python编程思想', price: 326, active: false},
        {id: 5, name: 'C++编程思想', price: 589, active: false}
      ],
      active: true,
    }
  },
  methods: {
    over(index) {
      for (let i = 0; i < this.books.length; i++) {
        if (index === i) {
          this.books[index].active = true;
        } else {
          this.books[i].active = false;
        }
      }
    },
    out(index, name) {
      console.log('确认要离开' + name + '的乐园吗');
    },
    add() {
      this.books.unshift({id: ++this.newId, name:this.name, price: 456, active: false});
      this.name = '';
      console.log(this.books);
    }
  }
}
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

.active {
  background: #888;
  color: white;
}
</style>