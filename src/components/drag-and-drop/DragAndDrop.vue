<script>
import { ref } from 'vue';

export default {
    setup () {
        const items = ref([
            { id: 0, title: 'Drag', list:1},
            { id: 1, title: '&', list:2},
            { id: 2, title: 'Drop', list:3},
        ])

        const getList = (list) => {
            return items.value.filter((item) => item.list == list)
        }

        const startDrag = (event, item) => {
            console.log(item);
            event.dataTransfer.dropEffect = 'move';
            event.dataTransfer.effectAllowed = 'move';
            event.dataTransfer.setData('itemID', item.id)

        }

        const onDrop = (event, list) => {
            const itemID = event.dataTransfer.getData('itemID');
            const item = items.value.find((item) => item.id == itemID);
            item.list = list;
        }

        return {
            getList,
            startDrag,
            onDrop
        }
    },
}
</script>

<template>
<div 
    class="drop-zone"
    @drop="onDrop($event, 1)"
    @dragenter.prevent
    @dragover.prevent
>
    <div 
        v-for="item in getList(1)"
        :key="item.id"
        class="drag-el"
        draggable="true"
        @dragstart="startDrag($event, item)"
    >
        {{ item.title }}
    </div>
</div>
<div 
    class="drop-zone"
    @drop="onDrop($event, 2)"
    @dragenter.prevent
    @dragover.prevent
>
    <div 
        v-for="item in getList(2)"
        :key="item.id"
        class="drag-el"
        draggable="true"
        @dragstart="startDrag($event, item)"
    >
        {{ item.title }}
    </div>
</div>
<div 
    class="drop-zone"
    @drop="onDrop($event, 3)"
    @dragenter.prevent
    @dragover.prevent
>
    <div 
        v-for="item in getList(3)"
        :key="item.id"
        class="drag-el"
        draggable="true"
        @dragstart="startDrag($event, item)"
    >
        {{ item.title }}
    </div>
</div>
</template>

<style scoped>
.drop-zone {
    display: flex;
    background-color: #3498db;
    border-radius: 0.6rem;
    padding: 1rem;
    min-height: 1rem;
    margin: 0.5rem;
}

.drop-zone:nth-of-type(2n+1) {
    background-color: rgb(124, 212, 212);
}

.drop-zone:nth-of-type(2n) {
    background-color: rgb(37, 188, 226);
}

.drag-el {
    border-radius: 1rem;
    background-color: #3498db;
    color: white;
    padding: 1rem;
    max-width: max-content;
    margin: 0.1rem;
}

.drag-el:nth-last-of-type(1) {
    margin-bottom: 0;
}

.drag-el:nth-of-type(2n) {
    background-color: rgb(37, 188, 226);
}
</style>