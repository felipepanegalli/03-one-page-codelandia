<template>
    <template v-if="label">
        <label :for="id">{{ label }}</label><br>
    </template>
    <input :id="id" :type="type" :placeholder="placeholder" :value="modelValue" @input="updateInput">
</template>

<script>
export default {
    name: "Input",
    props: {
        id: {type: String, required: true},
        label: {type: String, default: null},
        placeholder: {type: String, default: ''},
        type: {type: String, default: 'text'},
        modelValue: {type: [String, Number], default: ""},
    },
    methods: {
        updateInput(event) {
            this.$emit("update:modelValue", event.target.value);
        }
    }
}
</script>

<style lang="scss" scoped>
input {
    height: 65px;
    border: none;
    border-radius: 6px;
    padding: 0 1rem;
    font-size: 1.25rem;
    font-family: var(--font-lato);
    font-weight: 400;
    color: var(--gray);
    outline: none;

    &::placeholder {
        opacity: .7;
    }
}
</style>