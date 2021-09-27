<template>
    <div class="navbar">
        <NuxtLink to='/' class='btn'>
            <h3> Ledger </h3>
        </NuxtLink>
        <div>
            <NuxtLink to='/archive' class='btn'>
                <h3> Archive </h3>
            </NuxtLink>
            <NuxtLink to='/options' class='btn'>
                <h3> Options </h3>
            </NuxtLink>
            <span v-if="$auth.loggedIn">
                {{ $auth.user.email }}
                <b-btn text>Logout</b-btn>
            </span>
            <span v-else>
                <NuxtLink to="/login" class='btn'>Login</NuxtLink>
                <NuxtLink to="/register" class='btn'>Register</NuxtLink>
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>

</style>