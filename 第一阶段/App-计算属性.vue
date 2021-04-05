<template>
  <h2>{{ name }}-{{ slogen }}</h2>
  <h2>{{ getTitle() }}</h2>
  <h2>{{ getTitle() }}</h2>
  <h2>{{ getTitle() }}</h2>
  <h2>{{ title }}</h2>
  <h2>{{ title }}</h2>
  <h2>{{ title }}</h2>
  <br>
  总价：<small>￥</small>{{ books[0].price + books[1].price + books[2].price + books[3].price }}元
  <br>
  总价：<small>￥</small>{{ totalPrice }}元
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      name: '学习乐园',
      slogen: 'hello Vue',
      books: [
        {id: 1, name: '《三国演义》', price: 87},
        {id: 2, name: '《红楼梦》', price: 99},
        {id: 3, name: '《水浒传》', price: 121},
        {id: 4, name: '《西游记》', price: 162},
        {id: 4, name: '《西游记》', price: 162},
        {id: 4, name: '《西游记》', price: 162},
        {id: 4, name: '《西游记》', price: 162},
        {id: 4, name: '《西游记》', price: 162},
      ]
    }
  },
  computed: {// 计算属性带有缓存
    title: {
      get() {
        console.log('1111111');
        return this.name + '#' + this.slogen
      },
      set(newValue) {
        let arr = newValue.split('-');
        this.name = arr[0];
        this.slogen = arr[1];
      }
    },
    totalPrice: {
      get() {
        return this.books.reduce((s, n)=>s + n.price, 0)
      }
    }
  },
  methods: {
    getTitle() {
      console.log('222222222');
      this.title = '学习乐园-你好呀'
      return this.name + '-' + this.slogen
    }
  }
}
</script>

<style scoped>

</style>