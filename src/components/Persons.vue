<template>
  <div class="memo-container">
    <div class="list-container">
      <ul>
        <PersonList />
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import PersonList from '@/components/PersonList.vue';
@Component({
  components: {
    PersonList
  },
})
export default class Persons extends Vue {
  name = ""
}
</script>

<style scoped>
</style>