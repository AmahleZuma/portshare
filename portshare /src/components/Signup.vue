<template>
    <div>
        <h2>Sign up for an account</h2>
        <form @submit.prevent="handleSignup">
            <div>
                <label for="email">Email</label>
                <input id="email" type="email" v-model="email" />
            </div>
            <div>
                <label for="password">Password</label>
                <input id="password" type="password" v-model="password" />
            </div>
            <div>
                <button type="submit">Sign Up</button>
            </div>
        </form>
    </div>
</template>

<script setup>
import { ref } from "vue";
import { supabase } from "../supabase";

export default {
    setup() {
        const email = ref("");
        const password = ref("");

        const handleSignup = async () => {
            try {
                // Using supabase method for handling signups
                const { error } = await supabase.auth.singup({
                    email: email.value,
                    password: password.value,
                });
                if (error) throw error;
            } catch (error) {
                alert(error.error_description || error.message)
            }
        };

        return {
            email,
            password,
            handleSignup
        }
    }
}

</script>