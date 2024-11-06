<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import Table from "@/Components/Table.vue";
import TableRow from "@/Components/TableRow.vue";
import TableHeadCell from "@/Components/TableHeadCell.vue";
import TableDataCell from "@/Components/TableDataCell.vue";

defineProps(["roles"]);
</script>

<template>
    <Head title="List Roles" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <div class="flex justify-between">
                <h1>Roles Index Page</h1>

                <Link
                    :href="route('roles.create')"
                    class="px-3 py-2 text-white font-semibold bg-indigo-500 hover:bg-indigo-700 rounded"
                    >Create New Role</Link
                >
            </div>
            <div class="mt-6">
                <Table>
                    <template #header>
                        <TableRow>
                            <TableHeadCell>Id</TableHeadCell>
                            <TableHeadCell>Name</TableHeadCell>
                            <TableHeadCell>Action</TableHeadCell>
                        </TableRow>
                    </template>
                    <template #default>
                        <TableRow
                            v-for="role in roles"
                            :key="role.id"
                            class="border-b"
                        >
                            <TableDataCell>{{ role.id }}</TableDataCell>
                            <TableDataCell>{{ role.name }}</TableDataCell>
                            <TableDataCell>Edit/Delete</TableDataCell>
                        </TableRow>
                    </template>
                </Table>
            </div>
        </div>
    </AdminLayout>
</template>
