<script>
    const defaultIconPlay = ['fas', 'fa-play'];

    export default {
        props: {
            icon: {
                type: [String, Array],
                required: false,
                default () {
                    return defaultIconPlay;
                }
            }
        }
    }
</script>

<template>
  <button class="base-btn">
    <slot/>
  </button>
</template>

<style>
.base-btn {
    appearance: none;
    background: none;
    border: none;
    outline: none;
    cursor: pointer;

    font-weight: 700;
    padding: 1rem 2rem;
    margin: 0 1rem;
    
    color: white;
    background-color: #CC2E5D;
}

.base-btn:hover {
    opacity: 0.8;
}


</style>