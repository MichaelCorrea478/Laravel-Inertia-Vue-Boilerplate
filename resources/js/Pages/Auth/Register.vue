<script setup>
import { useForm } from '@inertiajs/vue3'

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null
})

</script>

<template>
    <div class="container w-50">
        <div class="card-body login-card-body">
            <p class="login-box-msg">Cadastrar</p>

            <form @submit.prevent="form.post('/register')">
                <!-- @csrf -->

                <div class="input-group mb-3">
                    <input type="text" name="name" class="form-control"
                           placeholder="Nome" required autocomplete="name" autofocus
                           v-model="form.name">
                    <div class="input-group-append">
                        <div class="input-group-text">
                            <span class="fas fa-user"></span>
                        </div>
                    </div>
                    <span class="error invalid-feedback" v-if="form.errors.name">
                        {{ form.errors.name }}
                    </span>
                </div>

                <div class="input-group mb-3">
                    <input type="email" name="email" class="form-control"
                           placeholder="Email" required autocomplete="email"
                           v-model="form.email">
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
                    <input type="password" name="password" class="form-control"
                           placeholder="Senha" required autocomplete="new-password"
                           v-model="form.password">
                    <div class="input-group-append">
                        <div class="input-group-text">
                            <span class="fas fa-lock"></span>
                        </div>
                    </div>
                    <span class="error invalid-feedback" v-if="form.errors.password">
                        {{ form.errors.password }}
                    </span>
                </div>

                <div class="input-group mb-3">
                    <input type="password" name="password_confirmation"
                           class="form-control"
                           placeholder="Confirmar senha" required autocomplete="new-password"
                           v-model="form.password_confirmation">
                    <div class="input-group-append">
                        <div class="input-group-text">
                            <span class="fas fa-lock"></span>
                        </div>
                    </div>
                </div>

                <div class="row">
                    <div class="col-12">
                        <button type="submit"
                                class="btn btn-primary btn-block">Cadastrar</button>
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>
