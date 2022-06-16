<template>
    <div class="btn" :class="{ 'btn-block': block }">
        Botão
    </div>
</template>

<script>
export default {
    name: "Default",
    props: { block: { type: Boolean } },
    setup() {


        return {}
    }
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
    box-shadow: 0px 5px 5px rgba(23, 23, 23, 0.1);
    border-radius: 5px;
    width: 155px;
}

.btn-block {
    width: 100%;
}
</style>