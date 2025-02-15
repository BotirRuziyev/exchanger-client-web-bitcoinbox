<template>
  <div class="form-input">
    <div v-if="mask != ''">
      <input
        :type="type"
        v-model="inputValue"
        :placeholder="placeholder"
        :maxlength="maxLength"
        :minlength="minLength"
        v-mask="mask"
        @input="$emit('update:modelValue', inputValue)"
      />
    </div>
    <div v-else>
      <input
        :type="type"
        v-model="inputValue"
        :placeholder="placeholder"
        :maxlength="maxLength"
        :minlength="minLength"
        @input="$emit('update:modelValue', inputValue)"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: String,
    type: { type: String, default: "text" },
    placeholder: String,
    mask: { type: String, default: "" },
    maxLength: { type: Number, default: 255 },
    minLength: { type: Number, default: 1 },
  },
  data() {
    return {
      inputValue: this.modelValue || "",
    };
  },
  watch: {
    modelValue(newVal) {
      this.inputValue = newVal;
    },
  },
};
</script>
