<template>
  <div class="container">
    <h1>Payment</h1>
    <input type="text" v-model="item1.name" placeholder="input name here" />
    <input
      type="text"
      v-model="item1.price"
      placeholder="input price here*under 50000"
    />
    <button id="clear" v-on:click="clear">Clear!</button>
    <div class="payment" ref="text">
      <label> {{ itemName }} </label>
      <label for="">{{ priceIsOver }}</label>
      <a v-bind:href="item1.url">amazon</a>
      <button v-on:click="buy(item1.name)">BUY IT</button>
    </div>
    <div class="payment">
      <label> {{ item2.name }} </label>
      <label>{{ item2.price }} yen</label>
      <a v-bind:href="item1.url">amazon</a>
      <button v-on:click="buy(item1.name)">BUY IT</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class Payment extends Vue {
  @Prop() private badget!: number;

  item1 = {
    name: "",
    price: "",
    url: "https://google.com",
  }

  item2 = {
    name: "sample",
    price: "40000",
    url: "https://amazon.co.jp/"
  }

  buy = (itemName: string) => {
    alert(`buy ${itemName}?`)
  }

  clear = () => {
    this.item1.name = "";
    this.item1.price = "";
  }

  get priceIsOver() {
    const pay = Number(this.item1.price);
    if (pay < this.badget) {
      return this.item1.price + " yen";
    } else {
      return "too expensive !!";
    }
  }

  get itemName() {
    if (this.item1.name == "") {
      return "sample";
    } else {
      return this.item1.name;
    }
  }

}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
label {
  font-size: 20px;
}
.payment {
  display: flex;
  justify-content: space-between;
  height: 80px;
  width: 400px;
  background-color: rgb(214, 214, 233);
  font-weight: bold;
  align-items: center;
  margin-bottom: 8px;
}
input {
  margin-bottom: 8px;
}
#clear {
  margin-bottom: 8px;
  padding: 2px 8px;
}
</style>
