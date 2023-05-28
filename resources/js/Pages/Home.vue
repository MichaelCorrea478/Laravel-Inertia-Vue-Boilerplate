<script setup>
import Layout from './Layouts/Layout.vue'
import { Head, usePage } from '@inertiajs/vue3'
import { computed } from 'vue'

const page = usePage()

const user = computed(() => page.props.auth.user)

</script>

<template>
  <Layout>
    <Head title="Home" />

    <div class="container-fluid p-3">
        <h1>Welcome - Home</h1>
        <p>Hello {{ user.name ?? '' }}, welcome to your first Inertia app!</p>
    </div>



  </Layout>
</template>
