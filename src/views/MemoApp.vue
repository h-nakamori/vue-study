<template>
  <div class="memo">
    <img alt="Vue logo" src="../assets/logo.png" />
    <memo />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Memo from '@/components/Memo.vue';
@Component({
  components: {
    Memo
  },
})
export default class HomeView extends Vue { }
</script>