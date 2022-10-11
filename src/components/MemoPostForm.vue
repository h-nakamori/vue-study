<template>
  <div class="form-container">
    <input type="text" v-model="desc" />
    <button id="post" class="save-button" @click="post()">POST</button>
  </div>
</template>

<script lang="ts">
import { Component, Emit, Vue } from 'vue-property-decorator';
@Component
export default class MemoPostForm extends Vue {
  desc = "";
  posted = "";

  @Emit()
  post() {
    if (this.desc == "") {
      alert("input any");
    } else {
      this.posted = this.desc;
      this.desc = "";
      return this.posted
    }
  }
}
</script>

<style scoped>
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

input {
  margin-bottom: 12px;
}
</style>