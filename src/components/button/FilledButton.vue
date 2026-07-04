<script lang="ts" setup>
const props = defineProps<{
  fullWidth?: boolean;
  type?: 'primary' | 'secondary' | 'tertiary';
}>();
</script>

<template>
  <button class="button" :class="{ 'full-width': props.fullWidth, 'primary': props.type === 'primary', 'secondary': props.type === 'secondary' || props.type === undefined, 'tertiary': props.type === 'tertiary' }">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.button {
  outline: 0;
  border: 0px;
  font-family: inherit;

  font-size: var(--lgd-comp-button-filled-text-size);
  line-height: var(--lgd-comp-button-filled-text-line-height);

  padding: var(--lgd-comp-button-filled-padding-vertical) var(--lgd-comp-button-filled-padding-horizontal);

  min-width: var(--lgd-comp-button-filled-min-width);

  border-radius: var(--lgd-comp-button-filled-border-radius);

  &.full-width {
    width: 100%;
  }

  &.primary {
    background-color: var(--lgd-comp-button-filled-primary-background-color);
    color: var(--lgd-comp-button-filled-primary-color);

    &:active {
      background-color: var(--lgd-comp-button-filled-primary-active-background-color);
    }
  }

  &.secondary {
    background-color: var(--lgd-comp-button-filled-secondary-background-color);
    color: var(--lgd-comp-button-filled-secondary-color);

    &:active {
      background-color: var(--lgd-comp-button-filled-secondary-active-background-color);
    }
  }

  &.tertiary {
    background-color: var(--lgd-comp-button-filled-tertiary-background-color);
    color: var(--lgd-comp-button-filled-tertiary-color);

    &:active {
      background-color: var(--lgd-comp-button-filled-tertiary-active-background-color);
    }
  }

  transition: background-color 0.1s ease-in-out;
}
</style>
