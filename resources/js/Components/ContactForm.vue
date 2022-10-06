<script setup>
import { useForm } from "@inertiajs/inertia-vue3";
import Form from '@/Components/Form.vue';

let form = useForm({
    first_name: "",
    last_name: "",
    email: "",
    phone: ""
});

const submit = (event) => {
    form = event;
    form.post(route('contacts.store'), {
        onFinish: () => form.reset()
    });
}
</script>

<template>
    <Form :contact="form" emitter="create" form-title="Add Contact" @create="submit($event)" />
</template>