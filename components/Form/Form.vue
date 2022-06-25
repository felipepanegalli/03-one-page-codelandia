<template>
    <form :id="id">
        <slot></slot>
    </form>
</template>

<script>
export default {
    name: "Form",
    props: {
        id: {type: String, required: true},
    }
}
</script>

<style lang="scss" scoped>
form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 100%;
}
</style>