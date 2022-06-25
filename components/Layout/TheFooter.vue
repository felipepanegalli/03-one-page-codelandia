<template>
    <div class="container">
        <Form id="formId">
            <h3 class="title">Entre em contato</h3>
            <Input placeholder="Nome" id="iptName" v-model="name"/>
            <Input type="email" placeholder="E-mail" id="iptEmail" v-model="email"/>
            <Input placeholder="Telefone" id="iptPhone" v-model="phone"/>
            <TextArea id="message" placeholder="Mensagem..." v-model="message"/>
            <Button text="Enviar mensagem" type="button" block @click="send"/>

            <p>Form formatado:</p>
            {{ JSONFormat }}

        </Form>
    </div>
</template>

<script>
import Button from "../Buttons/Button";
import Input from "../Form/Input";
import Form from "../Form/Form";
import TextArea from "../Form/TextArea";

export default {
    name: 'TheFooter',
    components: {TextArea, Form, Input, Button},
    computed: {
        JSONFormat() {
            return JSON.stringify({name: this.name, email: this.email, phone: this.phone, message: this.message})
        }
    },
    setup() {
        const name = ref('')
        const phone = ref('')
        const email = ref('')
        const message = ref('')

        function send() {
            alert('Este form envou os dados abaixo! ˆˆ')
        }

        return {name, phone, email, message, send}
    }
}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    justify-content: center;
    padding: 3rem 0;
    background-color: var(--purple-light);
    width: 100%;
    color: var(--gray);
}

#formId {
    width: 480px
}

.title {
    font-family: var(--font-merriweather);
    font-weight: 400;
    font-size: 2rem;
    text-align: center;
    margin: 1rem 0 2rem 0;
    line-height: 2rem;
}

@media only screen and (max-width: 480px) {
    #formId {
        width: 90%
    }

    .title {
        font-size: 2rem;
        text-align: center;
        margin: 1rem 0;
        line-height: 2.5rem;
    }
}
</style>