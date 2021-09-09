<script>
import Tab from './Tab.vue';
import TabsWrapper from './TabsWrapper.vue';

export default {
    components: {
        Tab,
        TabsWrapper
    }
};
</script>

<template>
    <tabs-wrapper>
        <tab title="Tab 1">Hello from Tab 1</tab>
        <tab title="Tab 2">Hello from Tab 2</tab>
        <tab title="Tab 3">Hello from Tab 3</tab>
        <tab title="Tab 4">Hello from Tab 4</tab>
    </tabs-wrapper>
</template>

<style>

</style>