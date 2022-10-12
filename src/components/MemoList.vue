<template>
  <div class="memo-container">
    <ul v-if="this.id != 0" class="ul">
      <li v-for="memo in memos" :key="memo.id" class="memo-list">
        <span>{{ memo.description }}</span>
        <button @click="deletePost(memo.id)" class="delete-button">
          DELETE
        </button>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Emit, Prop, Vue } from 'vue-property-decorator';

@Component
export default class MemoList extends Vue {
  @Prop() id!: number;
  @Prop() memos?: [{ id: number, description: string }]
  @Emit() deletePost(n: number) {
    return n;
  }
}
</script>

<style scoped>
span {
  font-weight: bold;
}

.memo-list {
  list-style: none;
  padding: 15px 20px;
  border-radius: 8px;
  background-color: rgb(250, 253, 219);
  margin-bottom: 20px;
  width: 400px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.memo-container {
  align-items: center;
}
.ul {
  margin: 0, auto;
  padding-inline-start: 0%;
}

button.delete-button {
  background-color: blanchedalmond;
  border: none;
  padding: 5px 8px;
  color: #7e0e0e;
  border-radius: 4px;
}

button.delete-button:hover {
  background-color: rgb(255, 189, 91);
}
</style>