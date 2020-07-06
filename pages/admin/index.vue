<template>
    <div class="admin-page">
        <section class="new-post">
            <AppButton @click="$router.push('/admin/new-post')">Create Post</AppButton>
        </section>
        <section class="existing-posts">
            <h1>Existing Posts</h1>
            <PostList isAdmin :posts="loadedPosts" />
        </section>
    </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    layout: "admin",
    asyncData(context: any) {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    loadedPosts: [
                        {
                            id: "1",
                            title: "First Post",
                            previewText: "This is our first post!",
                            thumbnail:
                                "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg"
                        },
                        {
                            id: "2",
                            title: "Second Post",
                            previewText: "This is our second post!",
                            thumbnail:
                                "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg"
                        }
                    ]
                });
            }, 1500);
        })
            .then(data => {
                return data;
            })
            .catch(e => {
                context.error(new Error());
            });
    }
});
</script>

<style scoped>
.admin-page {
    padding: 20px;
}

.new-post {
    text-align: center;
    border-bottom: 2px solid #ccc;
    padding-bottom: 10px;
}

.existing-posts h1 {
    text-align: center;
}
</style>
