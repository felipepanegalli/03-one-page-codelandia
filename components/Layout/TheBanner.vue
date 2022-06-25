<template>
    <div class="banner">
        <div class="left center">
            <h1>TechLow News</h1>
            <p class="my-3">
                O seu portal com informações, artigos e notícias sobre tecnologia, games, NFT e muito mais.
            </p>
            <Button text="Ver mais..." @click="seeMore"/>
        </div>
        <div class="right center">
            <img src="~/assets/images/gift.svg" alt="Gift illustration">
        </div>
    </div>
</template>

<script>
import Button from "../Buttons/Button";

export default {
    name: 'TheBanner',
    components: {Button},
    setup() {
        function seeMore() {
            alert('Clicou mas não valeu ashaushas...')
        }

        return {seeMore}
    }
}
</script>

<style lang="scss" scoped>
.banner {
    display: flex;
    flex-direction: row;
    min-height: 560px;
    background-color: var(--purple-light);
    width: 100%;
    color: var(--gray);

    .left {
        width: 50%;

        h1 {
            font-family: var(--font-merriweather);
            font-size: 2.25rem;
            line-height: 2.75rem;
            max-width: 380px;
        }

        p {
            font-family: var(--font-lato);
            max-width: 380px;
            font-size: 1.125rem;
            line-height: 2rem;
            font-weight: 400;
        }
    }

    .right {
        width: 50%;
        display: flex;

        img {
            max-height: 500px;
        }
    }
}

.center {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 5%;
}

.w-50 {
    width: 50%;
}

.my-3 {
    margin: 2rem 0;
}

@media only screen and (max-width: 480px) {
    .banner {
        flex-direction: column;
        min-height: 100%;

        .left {
            width: fit-content;

            h1 {
                font-size: 2rem;
                line-height: 2.5rem;
                max-width: 100%;
            }

            p {
                max-width: 100%;
            }
        }

        .right {
            width: fit-content;
            align-items: center;

            img {
                width: 100%;
            }
        }
    }

    .center {
        flex-direction: column;
        margin: 60px 20px;
    }
}
</style>