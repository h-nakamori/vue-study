<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <payment badget="50000" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Payment from '@/components/Payment.vue';
@Component({
  components: {
    Payment,
  },
})
export default class HomeView extends Vue { }
</script>
