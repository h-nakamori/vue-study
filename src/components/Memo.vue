<template>
  <div class="container">
    <h1>Memo App</h1>
    <memo-post-form @post="doPost" />
    <MemoList :id="id" :memos="memos" @delete-post="deletePost" />
    <p v-if="this.memosIsEmpty" class="no-memos">No memos has been posted</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import MemoPostForm from "@/components/MemoPostForm.vue";
import MemoList from "@/components/MemoList.vue";
@Component({
  components: {
    MemoPostForm,
    MemoList,
  }
})
export default class Memo extends Vue {

  id = 0;
  desc = ""; // insert from input string
  memos = [{ id: 0, description: "" }];
  memosIsEmpty = true;

  async doPost(e: string) {
    if (this.memosIsEmpty) {
      this.memosIsEmpty = false;
    }
    if (this.id == 0) {
      this.memos[0].id = 1;
      this.memos[0].description = e;
      this.id++;
      this.desc = "";
    } else {
      this.id++;
      let inputtingDesc = { id: this.id, description: "" };
      inputtingDesc.id = this.id;
      inputtingDesc.description = e;
      this.memos.push(inputtingDesc);
      this.desc = "";
    }
  }
  deletePost(id: number) {
    this.memos = this.memos.filter(t => t.id !== id);
    if (this.memos.length == 0) {
      this.memosIsEmpty = true;
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
</style>