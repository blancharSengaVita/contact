<script setup>

    import { ref } from 'vue';
    const data = ref([]);

    axios.get('/api/users')
    .then(function (response) {
        // handle success
        data.value = response.data.data;
    })

    console.log(data);
</script>

<template>
<table>
    <tr v-for="user in data">
        <td>
            <a @click="retrieveData">
                {{ user.email }}
            </a>
        </td>
    </tr>
</table>

</template>

<style scoped>

</style>
