<script setup>
import Navbar from './Navbar.vue'
import { Link } from '@inertiajs/vue3';
import Navigation from './Navigation.vue'
import Footer from './Footer.vue'

</script>

<template>
<div class="wrapper">

    <Navbar></Navbar>

    <!-- Main Sidebar Container -->
    <aside class="main-sidebar sidebar-dark-primary elevation-4">
        <!-- Brand Logo -->
        <Link :href="route('home')" class="brand-link">
            <img src="/images/AdminLTELogo.png" alt="AdminLTE Logo"
                class="brand-image img-circle elevation-3"
                style="opacity: .8">
            <span class="brand-text font-weight-light">FinApp</span>
        </Link>

        <Navigation></Navigation>
    </aside>

    <!-- Content Wrapper. Contains page content -->
    <div class="content-wrapper">
        <slot />
    </div>
    <!-- /.content-wrapper -->

    <!-- Control Sidebar -->
    <aside class="control-sidebar control-sidebar-dark">
        <!-- Control sidebar content goes here -->
        <div class="p-3">
            <h5>Title</h5>
            <p>Sidebar content</p>
        </div>
    </aside>
    <!-- /.control-sidebar -->

    <Footer></Footer>

</div>
</template>
