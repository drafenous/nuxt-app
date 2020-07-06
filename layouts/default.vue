<template>
    <div>
        <TheHeader @sidenavToggle="displaySidenav = !displaySidenav" />
        <TheSidenav :show="displaySidenav" @close="displaySidenav = false" />
        <Nuxt />
    </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
    data() {
        return {
            displaySidenav: false
        };
    }
});
</script>

<style>
html {
    font-family: "Open Sans", sans-serif;
}

body {
    margin: 0;
}
</style>
