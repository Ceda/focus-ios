<template>
  <div>
    <div
      class="select-wrapper"

    >
      <select
        v-model="selectedOption"
        @change="handleOptionChange"
        ref="select"
      >
       <option value="1">one</option>
  <option value="2">two</option>
  <option value="3">three</option>
  <option value="custom">custom</option>

      </select>
      <i
        class="dropdown-icon el-input__icon el-icon-arrow-down"
      />
    </div>
    <div
    >
      <input
        ref="customInput"
        id="customInput"
        v-model="customValue"
        :type="inputType"
      >
    </div>
    <button @click="focusInput">kkoko</button>
  </div>
</template>

<script>

export default {
  props: {
    options: {
      type: Array,
      default() {
        return [];
      },
    },
    value: [String, Number, null],
    showCustom: {
      type: Boolean,
      default: false,
    },
    inputType: {
      type: String,
      default: 'text',
    },
    dataValueType: {
      type: String,
      default: 'string',
    },
    optionSuffix: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      selectedOption: null,
      customValue: '',
      showCustomInput: false,
    };
  },
  methods: {
      logEvent(event) {
    console.log(event.type);
  },
    handleBlur() {
      this.$nextTick(() => {
        this.focusInput();
      });
    },
    focusInput() {
      this.$refs.customInput.focus();
    },
    handleOptionChange(event) {
      if (this.selectedOption === 'custom') {
        this.showCustomInput = true;
        console.log(event.type);
        this.focusInput();
      } else {
        this.showCustomInput = false;
      }
    },
  },
  mounted() {

  },

};
</script>

<style lang="scss">
  select, input {
    font-size: inherit;
    font-weight: 600;
    padding: .7rem 1rem;
    border-radius: 8px;
  }

.dropdown-icon {
  position: absolute;
  right: 5px;
  top: 50%;
  transform: translateY(-50%);
  pointer-events: none;
  color: rgb(42, 36, 36);
  font-weight: 600;
}

select:focus + .dropdown-icon {
  transform: translateY(-50%) rotate(180deg);
}

input:focus-visible {
  outline: 2px solid crimson;
  border-radius: 3px;
}

select:focus-visible {
  border: 2px dashed crimson;
  border-radius: 3px;
  outline: none;
}

</style>
