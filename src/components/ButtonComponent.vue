<template>
    <button class="py-4 text-lg rounded-full min-w-48 max-w-64" :class="themedButton" v-bind:="$attrs">
        {{ label }}
    </button>
</template>

<script setup>
import { computed } from 'vue';


const props = defineProps({
    label: {
        type: String,
        required: true
    },
    themed: {
        type: String,
        required: true,
        validator(value) {
            return [
                'primary',
                'outline'
            ].includes(value)
        }

    }
})


const themedButton = computed(() => {

    const themes = {
        primary: 'bg-black text-white',
        outline: 'border-solid border-2 border-black text-black hover:bg-black hover:text-white'
    };

    return themes[props.themed]
})
</script>

<style lang="scss" scoped></style>