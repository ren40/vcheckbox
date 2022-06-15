<template>
  <div class="v_checkbox_container">
    <input
      type="checkbox"
      :checked="isChecked"
      :name="nameCheckBox"
      :id="idCheckBox"
      :value="value"
      :disabled="disabled"
      :required="required"
      @change="changeChecked"
    />
    <slot name="v_label"
      ><label :for="idCheckBox">{{ labelText }}</label></slot
    >
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  isChecked: {
    type: Boolean,
    default: false,
  },
  idCheckBox: {
    type: String,
    required: true,
  },
  disabled: {
    type: Boolean,
    default: false,
  },
  required: {
    type: Boolean,
    default: false,
  },
  value: {
    type: String,
    default: "",
  },
  nameCheckBox: String,
  labelText: {
    type: String,
    default: "",
  },
});

const emits = defineEmits(["update:checked"]);

const changeChecked = (event) => {
  emits("update:checked", event.target.checked);
};
</script>

<style scoped>
.v_checkbox_container input[type="checkbox"] {
  display: none;
}

:slotted(label) {
  display: flex;
  margin-right: 5px;
  justify-content: center;
  align-items: center;
  font-size: 20px;
}

:slotted(label)::before {
  content: "";
  opacity: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 20px;
  height: 20px;
  border: 1px solid #e3e3;
  border-radius: 50%;
  margin-right: 5px;
  transition: 0.2s;
}

:slotted(label):hover::before {
  cursor: pointer;
}

input[type="checkbox"]:checked + :slotted(label)::before {
  background-color: red;
  content: "✓";
  color: #fff;
}

input[type="checkbox"]:disabled + :slotted(label) {
  opacity: 0.5;
}

input[type="checkbox"]:disabled + :slotted(label):hover::before {
  cursor: auto;
}
</style>