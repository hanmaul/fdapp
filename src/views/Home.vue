<template>
    {{ message }}
</template>
<script lang="ts">
import { onMounted, ref } from 'vue';

export default {
    name: "Home",
    setup() {
        const message = ref('You are not logged in!');
         
        onMounted(async () => {
            const response = await fetch('http://202.56.171.19:8085/fdapi/user', {
                headers: { 'Content-Type': 'application/json' },
                credentials: 'include'
            });

            const content = await response.json();

            message.value = `Hi ${content.userid}`;
        });

        return {
            message
        }
    }
}
</script>