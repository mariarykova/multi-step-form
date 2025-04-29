<template>
    <div class="input-group">
    <label class="label">{{ label }}</label>
    <div class="input-wrapper">
      <input
        :type="type"
        :placeholder="placeholder"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        class="input"
      />
      <img :src="icon" class="icon" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: String,
    label: {
      type: String,
      default: 'Label',
      required: true
    },
    type: {
      type: String,
      default: 'text',
      required: true
    },
    placeholder: {
      type: String,
      required: false,
      default: 'Placeholder'
    },
    icon: {
      type: String,
      required: false,
  }
  },
  emits: ['update:modelValue']
}
</script>

<style scoped>
.input-group {
  margin-bottom: 1rem;
  max-width: 284px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.label {
  font-weight: 500;
  line-height: 111%;
  color: var(--neutral-800);
}
.input-wrapper {
  max-width: 284px;
  width: 100%;
  position: relative;
}
.input {
  border: 1px solid var(--neutral-300);
  border-radius: 46px;
  max-width: 244px;
  width: 100%;
  box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
  background: var(--neutral-100);
  padding: 20px 40px 20px 20px;
  text-overflow: ellipsis;
  white-space: nowrap;
}


.input::placeholder {
  line-height: 111%;
  color: var(--neutral-600);
}
.input:focus {
  outline: none;
  border: 1px solid var(--primary-color-1);
  box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
  z-index: 2
}
.input.with-icon {
  padding-left: 0.5rem;
}
.icon {
  margin-right: 8px;
  color: #999;
  position: absolute;
  top: 0;
  right: 0px;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1
}

@media (max-width: 500px) {
  .input-group {
    gap: 10px;
}

.label {
    font-size: 14px;
}

.input {
    padding: 15px;
}

.icon {
    right: 17px;
}
}
</style>