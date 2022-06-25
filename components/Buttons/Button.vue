<template>
    <button class="btn" :class="{ 'btn-block': block }" :type="type">
        {{ text }}
    </button>
</template>

<script>
export default {
    name: "Button",
    props: {
        block: {type: Boolean},
        text: {type: String, default: 'Botão'},
        type: {type: String, default: 'button'}
    },
}
</script>

<style lang="scss" scoped>
.btn {
    height: 3.125rem;
    background-color: var(--purple);
    color: var(--white);
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.25rem;
    line-height: 1.5rem;
    font-family: var(--font-lato);
    box-shadow: 0 5px 5px rgba(23, 23, 23, 0.1);
    border-radius: 5px;
    width: 155px;
    cursor: pointer;
    border: none;

    &:hover {
        filter: brightness(1.2);
        box-shadow: 0 5px 5px rgba(23, 23, 23, 0.2);
    }
}

.btn-block {
    width: 100%;
}
</style>