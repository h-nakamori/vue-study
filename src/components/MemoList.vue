<template>
  <div class="memo-container">
    <!-- <p v-if="this.id == 0" class="no-memos">No memos has been posted</p>
    <ul v-if="this.id != 0" class="ul">
      <li v-for="memo in memos" :key="memo.id" class="memo-list">
        <span>{{ memo.description }}</span>
        <button @click="deletePost(memo.id)" class="delete-button">
          DELETE
        </button>
      </li>
    </ul> -->
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component
export default class MemoList extends Vue {
}
</script>

<style scoped>
</style>