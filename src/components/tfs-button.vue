<template>
    <button class="tfs-button" :disabled="disabled">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'tfs-button',
    props: {
        color: {
            type: String,
            default: '#3cc1e2'
        },
        colorHover: {
            type: String,
            default: '#6bdfff'
        },
        colorActive: {
            type: String,
            default: '#3cc1e2'
        },
        disabled: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style>
.tfs-button {
    min-width: 10rem;
    background-color: v-bind(color);
    border: none;
    color: white;
    padding: 15px 32px;
    margin: 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    transition: 0.3s ease-in-out;
    cursor: pointer;
    border-radius: 15px;
}

.tfs-button:hover {
    background-color: v-bind(colorHover);
}

.tfs-button:active {
    background-color: v-bind(colorActive);
}

.tfs-button:disabled {
    background-color: #cccccc;
    cursor: not-allowed;
}
</style>