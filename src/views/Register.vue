<template>
    <form @submit.prevent="submit">
        <h1 class="h3 mb-3 fw-normal">Please register</h1>

        <div class="form-floating">
            <input v-model="data.userid" type="text" class="form-control" id="floatingInput" placeholder="">
            <label for="floatingInput">User ID</label>
        </div>

        <div class="form-floating">
            <input v-model="data.password" type="password" class="form-control" id="floatingPassword"
                placeholder="Password">
            <label for="floatingPassword">Password</label>
        </div>

        <button class="w-100 btn btn-lg btn-primary" type="submit">Submit</button>

    </form>
</template>

<script lang="ts">
import { reactive } from 'vue';
import { useRouter } from 'vue-router';

export default {
    name: "Register",
    setup() {
        const data = reactive({
            userid: '',
            password: ''
        });

        const router = useRouter();

        const submit = async () => {
            await fetch('http://202.56.171.19:8085/fdapi/register', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(data)
            });

            await router.push('/login');
        }


        return {
            data,
            submit
        }
    }
}
</script>