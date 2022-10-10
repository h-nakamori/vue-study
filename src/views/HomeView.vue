<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <payment badget="50000" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import PaymentInput from '@/components/PaymentInput.vue'
import Payment from '@/components/Payment.vue';
@Component({
  components: {
    HelloWorld,
    Payment,
    PaymentInput,
  },
})
export default class HomeView extends Vue { }
</script>
