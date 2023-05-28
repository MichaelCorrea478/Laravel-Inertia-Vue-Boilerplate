<script setup>
import { Link } from '@inertiajs/vue3'
import { useForm } from '@inertiajs/vue3'

const form = useForm({
    email: null,
    password: null,
    remember: false
})


</script>

<template>
    <div class="container w-50">
        <div class="card-body login-card-body">
            <p class="login-box-msg">Login</p>

            <form @submit.prevent="form.post('/login')">
                <!-- @csrf -->

                <div class="input-group mb-3">
                    <input type="email" name="email" class="form-control" placeholder="Email" required autofocus v-model="form.email">
                    <div class="input-group-append">
                        <div class="input-group-text">
                            <span class="fas fa-envelope"></span>
                        </div>
                    </div>
                    <span class="error invalid-feedback" v-if="form.errors.email">
                        {{ form.errors.email }}
                    </span>
                </div>

                <div class="input-group mb-3">
                    <input type="password" name="password" class="form-control" placeholder="Senha" required v-model="form.password">
                    <div class="input-group-append">
                        <div class="input-group-text">
                            <span class="fas fa-lock"></span>
                        </div>
                    </div>
                    <span class="error invalid-feedback" v-if="form.errors.password">
                        {{ form.errors.password }}
                    </span>
                </div>

                <div class="row">
                    <div class="col-8">
                        <div class="icheck-primary">
                            <input type="checkbox" id="remember" name="remember" v-model="form.remember">
                            <label for="remember">
                                &nbsp;&nbsp;Lembrar me
                            </label>
                        </div>
                    </div>
                    <!-- /.col -->
                    <div class="col-4">
                        <button type="submit" class="btn btn-primary btn-block">Login</button>
                    </div>
                    <!-- /.col -->
                </div>
            </form>

            <!-- @if (Route::has('password.request')) -->
                <p class="mb-1">
                    <Link :href="route('password.request')">Esqueceu a senha?</Link>
                </p>
            <!-- @endif -->
        </div>
        <!-- /.login-card-body -->
    </div>
</template>
