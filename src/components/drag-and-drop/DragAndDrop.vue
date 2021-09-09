<script>
import { ref } from 'vue';

export default {
    setup () {
        const items = ref([
            { id: 0, title: 'Item A', list:1},
            { id: 1, title: 'Item B', list:1},
            { id: 2, title: 'Item C', list:2},
        ])

        const getList = (list) => {
            return items.value.filter((item) => item.list == list)
        }

        return {
            getList,
        }
    },
}
</script>

<template>
<div class="drop-zone">
    <div 
        v-for="item in getList(1)"
        :key="item.id"
        class="drag-el"
        draggable="true"
    >
        {{ item.title }}
    </div>
</div>
<div class="drop-zone">
    <div 
        v-for="item in getList(2)"
        :key="item.id"
        class="drag-el"
        draggable="true"
    >
        {{ item.title }}
    </div>
</div>
</template>

<style scoped>
.drop-zone {
    width: 50%;
    margin: 5rem auto;
    background-color: wheat;
    padding: 1rem;
    min-height: 1rem;
}

.drag-el {
    background-color: #3498db;
    color: white;
    padding: 0.5rem;
    margin-bottom: 1rem;
}

.drag-el:nth-last-of-type(1) {
    margin-bottom: 0;
}
</style>