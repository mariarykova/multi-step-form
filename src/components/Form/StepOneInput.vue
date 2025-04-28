<template>
    <div class="input-group">
    <label v-if="label" class="label">{{ label }}</label>
    <div class="input-wrapper">
      <span v-if="$slots.icon" class="icon">
        <slot name="icon" />
      </span>
      <input
        :type="type"
        :placeholder="placeholder"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        class="input"
        :class="{ 'with-icon': $slots.icon }"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: String,
    label: String,
    type: {
      type: String,
      default: 'text'
    },
    placeholder: String
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
    font-family: var(--font-family);
    font-weight: 500;
    font-size: 18px;
    line-height: 111%;
    color: var(--neutral-800);
}
.input-wrapper {
    max-width: 284px;
    width: 100%;
}
.input {
    border: 1px solid var(--neutral-300);
border-radius: 46px;
max-width: 244px;
width: 100%;
box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
background: var(--neutral-100);
padding: 20px;
}
.input::placeholder {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 18px;
    line-height: 111%;
    color: var(--neutral-600);
}
.input.with-icon {
  padding-left: 0.5rem;
}
.icon {
  margin-right: 8px;
  color: #999;
}
</style>