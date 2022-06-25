<template>
    <template v-if="label">
        <label :for="id">{{ label }}</label><br>
    </template>
    <textarea
        :id="id" cols="30" rows="10" 
        :placeholder="placeholder" 
        :value="modelValue"
        @input="updateInput"></textarea>
</template>

<script>
export default {
    name: "TextArea",
    props: {
        id: {type: String, required: true},
        label: {type: String, default: null},
        placeholder: {type: String, default: ''},
        modelValue: {type: String, default: ""},
    },
    methods: {
        updateInput(event) {
            this.$emit("update:modelValue", event.target.value);
        }
    }
}
</script>

<style lang="scss" scoped>
textarea {
    border: none;
    border-radius: 6px;
    padding: 1rem;
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