<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { Head } from "@inertiajs/vue3";
import Table from "@/Components/Table.vue";
import TableRow from "@/Components/TableRow.vue";
import TableHeadCell from "@/Components/TableHeadCell.vue";
import TableDataCell from "@/Components/TableDataCell.vue";

defineProps(["permissions"]);
</script>

<template>
    <Head title="List Permissions" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <h1>Permissions Index Page</h1>
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
                            v-for="permission in permissions"
                            :key="permission.id"
                            class="border-b"
                        >
                            <TableDataCell>{{ permission.id }}</TableDataCell>
                            <TableDataCell>{{ permission.name }}</TableDataCell>
                            <TableDataCell>Edit/Delete</TableDataCell>
                        </TableRow>
                    </template>
                </Table>
            </div>
        </div>
    </AdminLayout>
</template>
