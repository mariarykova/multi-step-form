<template>
    <label class="card-wrapper" :class="{ active: isChecked }">
      <input
        type="checkbox"
        class="hidden-input"
        :value="text"
        :checked="isChecked"
        @change="toggle"
        name="step-two"
      />
      <div class="circle">
        <img :src="icon" :alt="text" class="image" />
      </div>
      <div class="text">{{ text }}</div>
    </label>
  </template>
  
  <script>
  export default {
    name: 'StepTwoCard',
    props: {
      icon: {
        type: String,
        required: false
      },
      text: {
        type: String,
        required: true
      },
      modelValue: {
        type: Array,
        required: true
      }
    },
    computed: {
      isChecked() {
        return this.modelValue.includes(this.text);
      }
    },
    methods: {
      toggle(event) {
        const value = this.text;
        const newValue = [...this.modelValue];
  
        if (event.target.checked) {
          newValue.push(value);
        } else {
          const index = newValue.indexOf(value);
          if (index > -1) newValue.splice(index, 1);
        }
  
        this.$emit('update:modelValue', newValue);
      }
    }
  }
  </script>
  
  <style scoped>
  .card-wrapper {
    border: 1px solid var(--neutral-300);
    border-radius: 16px;
    box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
    background: var(--neutral-100);
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 15px;
    width: 100%;
    max-width: 255px;
    cursor: pointer;
    user-select: none;
  }
  .circle {
    border-radius: 100%;
    background-color: rgba(74, 58, 255, 0.15);
    width: 66px;
    height: 66px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .text {
    font-weight: 500;
    line-height: 111%;
    color: var(--neutral-800);
  }
  .card-wrapper.active {
    border: 1px solid var(--primary-color-1);
  }
  
  .hidden-input {
    position: absolute;
    opacity: 0;
    pointer-events: none;
    height: 0;
    width: 0;
  }
  
  @media (max-width: 500px) {
    .circle {
      width: 45px;
      height: 45px;
    }
  
    .image {
      width: 25px;
    }
  
    .text {
      font-size: 12px;
    }
  }
  </style>
  