<template>
  <div class="container">
    <h1>Memo App</h1>
    <div class="form-container">
      <input type="text" v-model="inputtingDesc" />
      <button id="post" class="save-button" @click="post()">post</button>
    </div>
    <div class="memo-container">
      <ul class="ul">
        <li v-for="memo in memos" :key="memo.id" class="memo-list">
          <span>{{ memo.id }}: {{ memo.description }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component
export default class Memo extends Vue {
  memos = [{ id: '1', description: 'hello world!' }, { id: '2', description: 'second memo!' }];
  inputtingDesc = "";

  post() {
    this.memos[0].description = this.inputtingDesc;
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
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
}

.memo-list {
  list-style: none;
}

span {
  font-weight: bold;
}

.memo-list {
  padding: 5px 8px;
  background-color: rgb(250, 253, 219);
  margin-bottom: 20px;
  width: 400px;
  height: 80px;
  align-items: center;
}

.memo-container {
  align-items: center;
}
.ul {
  margin: 0, auto;
  padding-inline-start: 0%;
}
</style>