<script setup>
import { Link } from '@inertiajs/inertia-vue3';

defineProps({
    contact: Object
});

defineEmits(['destroy']);
</script>

<template>
    <li>
        <div class="flex items-center px-4 py-4 sm:px-6">
            <div class="min-w-0 flex-1 sm:flex sm:items-center sm:justify-between">
                <div class="truncate">
                <div class="flex text-sm">
                    <p class="truncate font-medium text-indigo-600">{{ contact.first_name }} {{ contact.last_name }}</p>
                </div>
                <div class="mt-2 flex">
                    <div class="flex items-center text-sm text-gray-500 space-x-4">
                    <p>{{ contact.email }}</p>
                    <p>{{ contact.phone }}</p>
                    </div>
                </div>
                </div>
                <div class="mt-4 flex-shrink-0 sm:mt-0 sm:ml-5">
                    <div class="flex space-x-2 overflow-hidden">
                        <Link :href="route('contacts.edit', [contact.id])" class="inline-flex items-center rounded border border-transparent bg-indigo-600 px-2.5 py-1.5 text-xs font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Edit</Link>
                        <button @click="$emit('destroy', contact.id)" class="inline-flex items-center rounded border border-transparent bg-red-600 px-2.5 py-1.5 text-xs font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2">Delete</button>
                    </div>
                </div>
            </div>
        </div>
    </li>
</template>