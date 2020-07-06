<template>
    <div class="admin-post-page">
        <section class="update-form">
            <AdminPostForm :post="loadedPost" />
        </section>
    </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    layout: "admin",
    data() {
        return {
            loadedPost: {
                author: "Rodrigo",
                title: "My awesome Post",
                content: "Super amazing, thnsk for that!",
                thumbnailLink:
                    "http://static.pexels.com/photos/270348/pexels-photo-270348.jpeg"
            }
        };
    }
});
</script>

<style scoped>
.update-form {
    width: 90%;
    margin: 20px auto;
}

@media (min-width: 768px) {
    .update-form {
        width: 500px;
    }
}
</style>
