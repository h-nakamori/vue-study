<template>
  <div class="container">
    <h1>Payment</h1>
    <input type="text" v-model="item1.name" />
    <input type="text" v-model="item1.price" />
    <button v-on:click="clear">Clear!</button>
    <div class="payment" ref="text">
      <label> {{ item1.name }} </label>
      <label for="">{{ item1.price }}</label>
      <a v-bind:href="item1.url">amazon</a>
      <button v-on:click="buy(item1.name)">BUY IT</button>
    </div>
    <div class="payment">
      <label> {{ item2.name }} </label>
      <label>{{ item2.price }} yen</label>
    </div>
  </div>
</template>

<script lang="ts">
import { toRefs, watch } from 'vue';
import { Component, Prop, Ref, Vue, Watch } from 'vue-property-decorator';
@Component
export default class Payment extends Vue {
  @Prop() private badget!: number;

  item1 = {
    name: "item",
    price: "20000",
    url: "https://google.com",
  }

  item2 = {
    name: "item",
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
</style>
