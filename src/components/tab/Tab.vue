<script>
    import { inject } from 'vue';

    export default {
        props: ['title'],
        setup () {
            const selectedTitle = inject("selectedTitle");

            return {
                selectedTitle
            }
        }
    }
</script>

<template>
    <div class="tab-content" v-show="title == selectedTitle">
        <slot />
    </div>
</template>

<style scoped>
.tab-content {
    min-height: 20rem;
    padding: 2rem;
    border-radius: 0.5rem;
    box-shadow: 0 3px 5px 5px rgba(0, 0, 0, 0.05);
}
</style>