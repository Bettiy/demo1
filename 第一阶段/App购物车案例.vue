<template>
  <div v-if="carLists.length <= 0">你没有选择的商品，去购物</div>
  <table style="text-align: center" v-else>
    <caption><h1>购物车</h1></caption>
    <tr>
      <th></th>
      <th>编号</th>
      <th>商品名称</th>
      <th>商品价格</th>
      <th>商品数量</th>
      <th>操作</th>
    </tr>
    <tr v-for="(item, index) in carLists" :key="item.id">
      <td><input type="checkbox" v-model="item.checkbox"></td>
      <td>{{ item.id }}</td>
      <td>{{ item.name }}</td>
      <td>{{ item.price.toFixed(2) }}</td>
      <td>
        <button @click="item.count--" :disabled="item.count <= 1">-</button>
        {{ item.count }}
        <button @click="item.count++">+</button>
      </td>
      <td><a href="#" @click.prevent="del(index)">删除</a></td>
    </tr>
    <tr>
      <td colspan="3">总价</td>
      <td colspan="3"><small>￥</small>{{ totalPrice.toFixed(2) }}</td>
    </tr>
  </table>
</template>

<script>

export default {
  name: "App",
  components: {},
  data() {
    return {
      carLists: [
        {id: 1, checkbox: true, name: '《PHP指南》', price: 10, count: 1},
        {id: 2, checkbox: true, name: '《Vue指南》', price: 5, count: 1},
        {id: 3, checkbox: true, name: '《Java指南》', price: 15, count: 1},
        {id: 4, checkbox: true, name: '《Python指南》', price: 20, count: 1},
        {id: 5, checkbox: true, name: '《C++指南》', price: 30, count: 1},
        {id: 6, checkbox: true, name: '《ASP.NET指南》', price: 25, count: 1}
      ],
    }
  },
  methods: {
    del(index) {
      this.carLists.splice(index, 1);
    }
  },
  computed: {
    totalPrice: {
      get() {
        let sum = 0;
        for (let book of this.carLists) {
          if (book.checkbox) {
            sum += book.price * book.count;
          }
        }
        return sum;
      }
    }
  }
}
</script>

<style scoped>
table {
  width: 600px;
  border: 1px solid #888;
  border-collapse: collapse;
}

th {
  background: #ccc;
}

td, th {
  border: 1px solid #888;
  padding: 10px;
}
</style>