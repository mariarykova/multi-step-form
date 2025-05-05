<template>
    <label class="card-wrapper" :class="{ active: modelValue === text }">
      <input
        type="radio"
        class="hidden-input"
        :value="text"
        :checked="modelValue === text"
        @change="$emit('update:modelValue', text)"
        name="step-three"
      />
      <div class="circle" :class="{ 'active-circle': modelValue === text }"></div>
      <div class="text">{{ text }}</div>
    </label>
  </template>
  
  <script>
  export default {
    name: 'StepThreeSelect',
    props: {
      text: {
        type: String,
        default: 'Default Text',
        required: true
      },
      modelValue: {
        type: String,
        required: true
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
    padding: 30px 15px;
    width: 100%;
    max-width: 255px;
    cursor: pointer;
    user-select: none;
  }
  
  .circle {
    border-radius: 100%;
    background-color: var(--neutral-100);
    width: 24.7px;
    height: 24.7px;
    border: 1px solid var(--neutral-400);
    box-shadow: inset 0 -3px 7px 0 rgba(20, 20, 43, 0.08);
  }
  
  .circle.active-circle {
    border: 8.5px solid var(--primary-color-1);
    width: 9.7px;
    height: 9.7px;
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
    .card-wrapper {
      padding: 15px 10px;
    }
  
    .text {
      font-size: 14px;
    }
  
    .circle {
      width: 20.7px;
      height: 20.7px;
    }
  
    .circle.active-circle {
      width: 5.7px;
      height: 5.7px;
    }
  }
  </style>
  