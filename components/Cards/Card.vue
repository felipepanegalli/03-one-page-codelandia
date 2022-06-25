<template>
    <div class="card">
        <div class="card__cover">
            <img :src="imgSrc" :alt="title"/>
        </div>
        <div class="card__text">
            <h3>{{ title }}</h3>
            <p>{{ subtitle }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: {
        imgSrc: {type: String, required: true},
        title: {type: String, required: true},
        subtitle: {type: String, required: true},
    },
    setup() {
        return {}
    }
}
</script>

<style lang="scss" scoped>
.card {
    background-color: var(--white);
    margin-bottom: 1.75rem;
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    box-shadow: 0 0 1.25rem rgba(0, 0, 0, 0.1);
    max-width: 375px;
    min-width: 192px;

    .card__cover {
        img {
            width: 100%;
        }
    }

    .card__text {
        display: flex;
        flex-direction: column;
        padding: 2rem;
        
        h3 {
            font-weight: 700;
            font-size: 1.5rem;
            line-height: 1.875rem;
            font-family: var(--font-merriweather);
            margin-bottom: 1.5rem;
            color: var(--gray-dark);
        }

        p {
            font-weight: 400;
            font-size: 1.125rem;
            line-height: 1.875rem;
            font-family: var(--font-lato);
            color: var(--gray);
        }
    }
}
</style>