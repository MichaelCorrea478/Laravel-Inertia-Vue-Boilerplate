<script setup>
import Layout from './Layouts/Layout.vue';
import { Head } from '@inertiajs/vue3'

defineProps({ name: String })
</script>

<template>
  <Layout>
    <Head title="Welcome" />
    <h1>Welcome</h1>
    <p>Hello {{ name }}, welcome to your first Inertia app!</p>
  </Layout>
</template>
