<template>
  <div class="container">
    <h1>Memo App</h1>
    <div class="form-container">
      <input type="text" v-model="desc" />
      <button id="post" class="save-button" @click="post()">post</button>
    </div>
    <div class="memo-container">
      <ul class="ul">
        <li v-for="memo in memos" :key="memo.id" class="memo-list">
          <span>{{ memo.description }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component
export default class Memo extends Vue {
  memos = [{ id: 0, description: "sample memo!" }];
  desc = ""; // insert from input string

  post() {
    if (this.desc == "") {
      alert('input anyy')
    } else {
      let inputtingDesc = { id: 0, description: "" };
      inputtingDesc.id = Math.round(Math.random() * 10);
      inputtingDesc.description = this.desc;
      this.memos.push(inputtingDesc);
      this.desc = "";
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

.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 300px;
  margin-bottom: 12px;
  border-radius: 4px;
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
  justify-content: center;
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
</style>