<script setup>
import Layout from './Layouts/Layout.vue'
import { Head } from '@inertiajs/vue3'

defineProps({ name: String })
</script>

<template>
  <Layout :name="name">
    <Head title="Home" />

    <div class="container-fluid">
        <h1>Welcome - Home</h1>
        <p>Hello {{ name }}, welcome to your first Inertia app!</p>
    </div>



  </Layout>
</template>
