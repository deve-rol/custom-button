<template>
    <button :class="['button', size, variant]" :disabled="disabled">
        <slot>Button</slot>
    </button>
</template>

<script>
    export default {
        name: "customButton",
        props: {
            size: {
                type: String
            },
            variant: {
                type: String
            },
            disabled: {
                type: Boolean,
                default: false
            }
        }
    }
</script>

<style lang="scss" scoped>
.button {
    border: none;
    border-radius: 4px;
    padding: 8px 12px;
    font-size: 16px;
    font-weight: bold;
    color: #ffffff;
    background-color: #4caf50;
    cursor: pointer;
    box-shadow: 0 1px 3px 1px rgba(0, 0, 0, 0.1);
    transition: all .2s;

    &:hover {
        box-shadow: 0 2px 4px -1px rgba(0, 0, 0, 0.2), 0px 4px 5px 0px rgba(0, 0, 0, 0.14), 0px 1px 10px 0px rgba(0,0,0,.12);
    }
    &.lg {
        padding: 14px 20px;
        font-size: 20px;
    }
    &.sm {
        padding: 4px 6px;
        font-size: 12px;
    }
    &.success {
        background-color: #4caf50;
    }
    &.text {
        background-color: transparent;
        color: #1867c0;
        box-shadow: none;
        &:hover {
            background-color: #fafafa;
        }
    }
    &.primary {
        background-color: #1867c0;
    }
    &.danger {
        background-color: #ff5252;
    }
    &.warning {
        background-color: #fb8c00;
    }
    &:disabled {
        background-color: #d6d6d6;
        color: #777777;
        box-shadow: none;
        cursor: default;
    }
}
</style>