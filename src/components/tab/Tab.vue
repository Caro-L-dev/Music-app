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
    <div>
        <slot />
    </div>
</template>