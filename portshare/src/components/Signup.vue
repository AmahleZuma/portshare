<template>
    <div class="container">
        <h2>Sign Up</h2>
        <form>
            <label for="email">Email</label>
            <input v-model="text" placeholder="you@organization.com">
            <label for="password">Password</label>
            <input v-model="text" placeholder="password123(Don't use this. If you do, you have skill issues)">
        </form>
    </div>

</template>

<script setup>

</script>

<style lang="css" scoped>

    .container {
        margin-top: 70px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    form {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>