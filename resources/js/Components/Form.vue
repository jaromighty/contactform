<script setup>
import InputError from "@/Components/InputError.vue";

defineProps({
    contact: Object,
    emitter: String,
    formTitle: String
});

defineEmits(['create']);
</script>

<template>
    <div class="overflow-hidden bg-white py-16 px-4 sm:px-6 lg:px-8 lg:py-24">
        <div class="relative mx-auto max-w-xl">
        <svg class="absolute left-full translate-x-1/2 transform" width="404" height="404" fill="none" viewBox="0 0 404 404" aria-hidden="true">
            <defs>
            <pattern id="85737c0e-0916-41d7-917f-596dc7edfa27" x="0" y="0" width="20" height="20" patternUnits="userSpaceOnUse">
                <rect x="0" y="0" width="4" height="4" class="text-gray-200" fill="currentColor" />
            </pattern>
            </defs>
            <rect width="404" height="404" fill="url(#85737c0e-0916-41d7-917f-596dc7edfa27)" />
        </svg>
        <svg class="absolute right-full bottom-0 -translate-x-1/2 transform" width="404" height="404" fill="none" viewBox="0 0 404 404" aria-hidden="true">
            <defs>
            <pattern id="85737c0e-0916-41d7-917f-596dc7edfa27" x="0" y="0" width="20" height="20" patternUnits="userSpaceOnUse">
                <rect x="0" y="0" width="4" height="4" class="text-gray-200" fill="currentColor" />
            </pattern>
            </defs>
            <rect width="404" height="404" fill="url(#85737c0e-0916-41d7-917f-596dc7edfa27)" />
        </svg>
        <div class="text-center">
            <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">{{ formTitle }}</h2>
        </div>
        <div class="mt-12">
            <form @submit.prevent="$emit(emitter, contact)" class="grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
            <div>
                <label for="first-name" class="block text-sm font-medium text-gray-700">First name</label>
                <div class="mt-1">
                <input type="text" name="first-name" id="first-name" v-model="contact.first_name" autocomplete="given-name" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
                <InputError class="mt-1" :message="contact.errors.first_name" />
                </div>
            </div>
            <div>
                <label for="last-name" class="block text-sm font-medium text-gray-700">Last name</label>
                <div class="mt-1">
                <input type="text" name="last-name" id="last-name" v-model="contact.last_name" autocomplete="family-name" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
                <InputError class="mt-1" :message="contact.errors.last_name" />
                </div>
            </div>
            <div class="sm:col-span-2">
                <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                <div class="mt-1">
                <input id="email" name="email" type="email" v-model="contact.email" autocomplete="email" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
                <InputError class="mt-1" :message="contact.errors.email" />
                </div>
            </div>
            <div class="sm:col-span-2">
                <label for="phone-number" class="block text-sm font-medium text-gray-700">Phone Number</label>
                <div class="relative mt-1 rounded-md shadow-sm">
                <div class="absolute inset-y-0 left-0 flex items-center">
                    <label for="country" class="sr-only">Country</label>
                    <select id="country" name="country" class="h-full rounded-md border-transparent bg-transparent py-0 pl-4 pr-8 text-gray-500 focus:border-indigo-500 focus:ring-indigo-500">
                    <option>US</option>
                    <option>CA</option>
                    <option>EU</option>
                    </select>
                </div>
                <input type="text" name="phone-number" id="phone-number" v-model="contact.phone" autocomplete="tel" class="block w-full rounded-md border-gray-300 py-3 px-4 pl-20 focus:border-indigo-500 focus:ring-indigo-500" placeholder="+1 (555) 987-6543" />
                </div>
                <InputError class="mt-1" :message="contact.errors.phone" />
            </div>
            <div class="sm:col-span-2">
                <button type="submit" class="inline-flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-6 py-3 text-base font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Add new contact</button>
            </div>
            </form>
        </div>
        </div>
    </div>
</template>