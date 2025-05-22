<script setup>
import { computed } from 'vue';
import { Link } from '@inertiajs/vue3';

const emit = defineEmits(['click']);

const props = defineProps({
    href: {
        type: String,
        required: true,
    },
    active: {
        type: Boolean,
    },
});

const classes = computed(() =>
    props.active
        ? 'inline-flex items-center px-1 pt-1 border-b-2 border-indigo-400 text-sm font-medium leading-5 text-white transition duration-150 ease-in-out'
        : 'inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium leading-5 text-white hover:text-gray-400 hover:border-gray-300 transition duration-150 ease-in-out'
);
</script>

<template>
    <a :href="href" :class="classes" @click="$emit('click')">
        <slot />
    </a>
</template>
