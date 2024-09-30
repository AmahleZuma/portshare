<template>
    <div>
        <sign-up v-if="isSignup"/>
        <sign-in v-else />
        <button @click="isSignup = !isSignup">

            {{ 
                isSignup
                ? "Already have an account? Sign In"
                : "Don't have an account yet? Sign Up"
            }}

        </button>
    </div>
</template>

<script setup>
import { ref } from "vue";
import Signup from "./Signup.vue";
import Signin from "./Signin.vue";
export default {
    components: { Signup, SignIn },
    setup() {
        const isSignup = ref(true);

        return {
            isSignup,
        };
    },
};
</script>

<style scoped></style>