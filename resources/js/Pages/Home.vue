<script setup>
import Layout from './Layout.vue';
import { Head } from '@inertiajs/vue3'

defineProps({ name: String })
</script>

<template>
  <Layout>
    <Head title="Welcome" />
    <h1>Welcome - Home</h1>
    <p>Hello {{ name }}, welcome to your first Inertia app!</p>
  </Layout>
</template>