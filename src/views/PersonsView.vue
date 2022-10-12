<template>
  <div class="memo">
    <img alt="Vue logo" src="../assets/logo.png" />
    <persons />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Persons from '@/components/Persons.vue';
@Component({
  components: {
    Persons
  },
})
export default class PersonsView extends Vue {
}
</script>

<style scoped>
</style>