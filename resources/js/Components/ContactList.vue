<script setup>
import ContactItem from '@/Components/ContactItem.vue';
import { Inertia } from '@inertiajs/inertia';

defineProps({
    contacts: Array
});

const destroy = (id) => {
    Inertia.delete(route('contacts.destroy', [id]));
}
</script>

<template>
    <ul role="list" class="relative mx-auto max-w-xl divide-y divide-gray-200">
        <ContactItem v-for="contact in contacts" :key="contact.id" :contact="contact" @destroy="destroy" />
    </ul>
</template>