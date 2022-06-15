<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import vcheckbox from "./components/VCheckbox.vue";

import { ref } from "vue";

const idCheckBoxExampleOne = ref("test1");
const idCheckBoxExampleTwo = ref("test2");
const idCheckBoxExampleThree = ref("test3");
</script>

<template>
  <div class="container">
    <h1>VCheckbox</h1>
    <div class="section_body">
      <p>Пример компонента VCheckbox</p>
      <div class="example">
        <vcheckbox
          :idCheckBox="idCheckBoxExampleOne"
          labelText="Hello world"
        ></vcheckbox>
      </div>
      <p>Пример с другими режимами</p>
      <div class="other_example">
        <div class="disabled_example">
          <p>Заблокированный</p>
          <vcheckbox
            :idCheckBox="idCheckBoxExampleTwo"
            disabled
            labelText="Hello world"
          ></vcheckbox>
        </div>
        <div class="slot_example">
          <p>Использование slot</p>
          <vcheckbox :idCheckBox="idCheckBoxExampleThree">
            <template #v_label>
              <label :for="idCheckBoxExampleThree"> Other message</label>
            </template>
          </vcheckbox>
        </div>
      </div>
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
  width: 100%;
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
  width: 50vw;
}

.section_body p {
  text-align: center;
  font-size: 20px;
  font-weight: 600;
}

.other_example {
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  align-items: center;
}
</style>
