<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import Checkbox from "@/Components/Checkbox.vue";
import InputError from "@/Components/InputError.vue";
import InputLabel from "@/Components/InputLabel.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import TextInput from "@/Components/TextInput.vue";
import { Head, Link, useForm } from "@inertiajs/vue3";

const form = useForm({
    name: "",
});
</script>

<template>
    <Head title="Create New Role" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <div class="flex justify-between">
                <h1>Create New Role Page</h1>

                <Link
                    :href="route('roles.index')"
                    class="px-3 py-2 text-white font-semibold bg-indigo-500 hover:bg-indigo-700 rounded"
                    >Go Back</Link
                >
            </div>
            <div class="mt-6 max-w-md mx-auto">
                <form @submit.prevent="form.post(route('roles.store'))">
                    <div>
                        <InputLabel for="name" value="Name" />

                        <TextInput
                            id="name"
                            type="name"
                            class="mt-1 block w-full"
                            v-model="form.name"
                        />

                        <InputError class="mt-2" :message="form.errors.name" />
                    </div>

                    <div class="flex items-center mt-4">
                        <PrimaryButton
                            class="ms-4"
                            :class="{ 'opacity-25': form.processing }"
                            :disabled="form.processing"
                        >
                            Create Data
                        </PrimaryButton>
                    </div>
                </form>
            </div>
        </div>
    </AdminLayout>
</template>
