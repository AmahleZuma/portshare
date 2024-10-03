<template><
    <div>>
        <h2>Sign in to your account</h2>
        <form @submit.prevent="handleSingin">
            <div>
                <label for="email">Email</label>
                <input id="email" type="email" v-model="email" />
            </div>
            <div>
                <label for="password">Password</label>
                <input id="password" type="password" v-model="password" />
            </div>
            <button type="submit">Sign In</button>
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

        const handleSingin = async () => {
            try {
                // Using supabase method
                const { error } = await supabase.auth.signInAnonymously({
                    email: email.value,
                    password: password.value,
                });
                if ( error ) throw error;
            } catch ( error ) {
                alert(error.error_description || error.message);
            }
        };

        return {
            email,
            password,
            handleSingin,
        };
    },
};

</script>
