<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import vcheckbox from "./components/VCheckbox.vue";

import { ref } from "vue";

const idCheckBox = ref("test1");
</script>

<template>
  <div class="container">
    <h1>VCheckbox</h1>
    <div class="section_body">
      <p>Пример компонента VCheckbox</p>
      <vcheckbox :idCheckBox="idCheckBox" labelText="Hello world"></vcheckbox>
    </div>
  </div>
</template>

<style>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 10px;
}

h1::first-letter {
  color: rgb(61, 228, 61);
}

h1 {
  color: rgb(54, 54, 54);
}

.section_body {
  display: flex;
  flex-direction: column;
}
</style>
