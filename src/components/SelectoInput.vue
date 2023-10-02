<template>
  <div>
    <select :class="{ hidden: isCustomValue }" v-model="selectedValue" @change="handleChange">
      <option v-for="option in options" :key="option.value" :value="option.value">
        {{ option.text }}
      </option>
      <option value="custom">Custom</option>
    </select>
    <input
      :class="{ hidden: !isCustomValue }"
      ref="input"
      v-model="customValue"
      @blur="handleBlur"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedValue: "",
      customValue: "",
      isCustomValue: false,
      options: [
        { value: "option1", text: "Option 1" },
        { value: "option2", text: "Option 2" },
      ],
    };
  },
  methods: {
    handleChange() {
      if (this.selectedValue === "custom") {
        const value = window.prompt('Enter your custom value:');
        if (value) {
          this.customValue = value;
          this.isCustomValue = true;
        } else {
          this.selectedValue = ''; // Reset to default or another value if necessary
        }
      }
    },
    handleBlur() {
      if (this.customValue === "") {
        this.isCustomValue = false;
      }
    },
  },
};
</script>

<style scoped>
.hidden {
  display: none;
}
</style>
