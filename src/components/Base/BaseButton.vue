<template>
    <button
      :type="type"
      :class="['base-button', variant, size]"
      @click="$emit('click', $event)"
    >
      <slot />
    </button>
  </template>
  
  <script>
  export default {
    inheritAttrs: false,
    props: {
      type: {
        type: String,
        default: 'button'
      },
      variant: {
        type: String,
        default: 'primary'
      },
      size: {
        type: String,
        default: 'default'
      },
      disabled: {
        type: Boolean,
        default: false
      }
    },

  }
  </script>
  
  <style scoped>
  .base-button {
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 18px;
    line-height: 111%;
    border: none;
    cursor: pointer;
    border-radius: 56px;
    padding: 20px 40px;
  }
  
  .primary {
    background: var(--primary-color-1);
    color: var(--neutral-100);
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
  }
  .primary:hover {
   background: var(--neutral-100);
    color: var(--primary-color-1);
  }
  
  .secondary {
    background: var(--neutral-100);
    color: var(--primary-color-1);
    border: 1px solid var(--primary-color-1);
  }
  .secondary:hover {
    background: var(--primary-color-1);
    color: var(--neutral-100);
    border: 1px solid var(--primary-color-1);
  }
  
  .small {
    font-size: 14px;
    padding: 10px 20px;
  }
  .large {
    font-size: 20px;
    padding: 22px 48px;
  }
  .full-width {
    width: 100%;
  }

  @media (max-width: 500px) {
    .base-button {
      padding: 10px 20px;
      font-size: 14px;
    }
    .primary {
      padding: 10px 20px;
    }
    .secondary {
      padding: 10px 20px;
    }
  }
  
  </style>
  