<script setup>
import { Head } from '@inertiajs/inertia-vue3';
import { Inertia } from '@inertiajs/inertia';
import Form from '@/Components/Form.vue';

const props = defineProps({
    contact: Object,
});

const submit = () => {
    Inertia.put(route('contacts.update', [props.contact.id]), props.contact);
}
</script>

<template>
    <Head title="Edit Contact" />

    <Form :contact="contact" emitter="create" form-title="Edit Contact" @create="submit($event)" />
</template>