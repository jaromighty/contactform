<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';
import ContactForm from '@/Components/ContactForm.vue';
import ContactList from '@/Components/ContactList.vue';

defineProps({
    contacts: Array
})
</script>

<template>
    <Head title="Contact Form" />

    <ContactForm />
    <ContactList :contacts="contacts" />
</template>
