<template>
  <div class="container">
    <h1>Memo App</h1>
    <div class="form-container">
      <input type="text" v-model="desc" />
      <button id="post" class="save-button" @click="post()">POST</button>
    </div>
    <div class="memo-container">
      <p v-if="this.id == 0" class="no-memos">No memos has been posted</p>
      <ul v-if="this.id != 0" class="ul">
        <li v-for="memo in memos" :key="memo.id" class="memo-list">
          <span>{{ memo.description }}</span>
          <button @click="deletePost(memo.id)" class="delete-button">
            DELETE
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component
export default class Memo extends Vue {

  id = 0;
  desc = ""; // insert from input string
  memos = [{ id: 0, description: "" }];

  post() {
    if (this.desc == "") {
      alert('input anyy');
    } else if (this.id == 0) {
      this.memos[0].id = 1;
      this.memos[0].description = this.desc;
      this.id++;
      this.desc = "";
    } else {
      this.id++;
      let inputtingDesc = { id: this.id, description: "" };
      inputtingDesc.id = this.id
      inputtingDesc.description = this.desc;
      this.memos.push(inputtingDesc);
      this.desc = "";
    }
  }
  deletePost(id: number) {
    this.memos = this.memos.filter(t => t.id !== id);
  }
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 400px;
  height: 100px;
  margin-bottom: 12px;
  border-radius: 4px;
  justify-content: center;
}

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
input {
  margin-bottom: 12px;
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

button.save-button {
  background-color: #e2dce3;
  border: none;
  padding: 9px 27px;
  color: #ef918a;
  border-radius: 4px;
}

button.save-button:hover {
  background-color: #cec7cf;
}
</style>