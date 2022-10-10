<template>
  <input v-on:input="input" />
</template>

<script lang="ts">
import { Component, Prop, Ref, Vue, Watch } from 'vue-property-decorator';

@Component
export default class PaymentInput extends Vue {
  @Prop() public itemName?: string;

  input($event: any) {
    this.itemName = $event.target.value;
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
