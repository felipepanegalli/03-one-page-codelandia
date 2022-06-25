<template>
    <LayoutContainer>
        <LayoutTheBanner/>
        <div class="content">
            <template v-if="pending">
                <h3>Loading ...</h3>
            </template>
            <template v-else>
                <div v-for="post in posts">
                    <CardsCard
                        :img-src="post.urlToImage"
                        :title="post.title"
                        :subtitle="post.description"
                        data-aos="zoom-in"
                        data-aos-duration="1000"
                    />
                </div>
            </template>
        </div>
        <LayoutTheFooter/>
    </LayoutContainer>
</template>

<script>

</script>

<script>
import axios from "axios";
import aos from "./mixins/aos";

export default {
    mixins: [aos],
    async setup() {
        const pending = ref(true);
        const posts = ref([]);

        const news = await axios.get('http://localhost:3000/api/articles')
        posts.value = news.data.articles
        pending.value = false;

        return {pending, posts}
    }
}
</script>

<style lang="scss" scoped>
.content {
    padding: 40px 20px;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: center;
}
</style>