<template>
    <div class="banner">
        <div class="left center">
            <h1>Lorem ipsum dolor sit amet</h1>
            <p class="my-3">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas eu massa sit amet augue
                consectetur
                ullamcorper non ac massa.</p>
            <ButtonsDefault />
        </div>
        <div class="right center">
            <img src="~/assets/images/gift.svg" alt="Gift illustration">
        </div>
    </div>
</template>

<script>
export default {
    name: 'TheBanner',
    setup() {


        return {}
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