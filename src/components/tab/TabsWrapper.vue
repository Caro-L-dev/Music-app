<script>
import { ref, provide } from 'vue';

    export default {
        setup (props, { slots } ) {
            const tabTitleList = ref(slots.default().map((tab) => tab.props.title));
            const selectedTitle = ref(tabTitleList.value[0]);


            provide("selectedTitle", selectedTitle)
            return {
                selectedTitle,
                tabTitleList
            }
        }
    }
</script>

<template>
    <div class="tabs">
        <ul class="tabs__header">
            <li 
                v-for="title in tabTitleList"   
                :key="title"
                @click="selectedTitle = title"
            >
                 {{ title }}
            </li>
        </ul>
        <slot />
    </div>
</template>
    
