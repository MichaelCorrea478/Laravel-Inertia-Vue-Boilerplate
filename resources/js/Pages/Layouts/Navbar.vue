<script setup>
import { Link, usePage } from '@inertiajs/vue3'
import { computed } from 'vue'

const page = usePage()

const user = computed(() => page.props.auth.user)

</script>

<template>
        <!-- Navbar -->
        <nav class="main-header navbar navbar-expand navbar-white navbar-light">
        <!-- Left navbar links -->
        <ul class="navbar-nav">
            <li class="nav-item">
                <a class="nav-link" data-widget="pushmenu" href="#" role="button"><i class="fas fa-bars"></i></a>
            </li>
        </ul>

        <!-- Right navbar links -->
        <ul class="navbar-nav ml-auto">
            <li class="nav-item dropdown">
                <a class="nav-link" data-bs-toggle="dropdown" href="#" aria-expanded="false">
                    {{ user.name ?? '' }}
                </a>
                <div class="dropdown-menu dropdown-menu-right" style="left: inherit; right: 0px;">
                    <a href="#" class="dropdown-item">
                        <i class="mr-2 fas fa-file"></i>
                        Meu perfil
                    </a>
                    <div class="dropdown-divider"></div>
                    <!-- <form method="POST" action="{{ route('logout') }}"> -->
                        <!-- @csrf -->
                        <Link :href="route('logout')" method="POST" as="button" class="dropdown-item">
                        <!-- onclick="event.preventDefault(); this.closest('form').submit();"> -->
                            <i class="mr-2 fas fa-sign-out-alt"></i>
                            Logout
                        </Link>
                    <!-- </form> -->
                </div>
            </li>
        </ul>
    </nav>
    <!-- /.navbar -->
</template>
