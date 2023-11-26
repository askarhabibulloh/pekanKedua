import type { pushScopeId } from 'vue'; import type { useRoute } from
'vue-router';
<script setup lang="ts">
import { useAuthStore } from "@/stores/auth";
import axios from "axios";
import { ref } from "vue";
import { useRouter } from "vue-router";

const auth = useAuthStore();
const username = ref("");
const password = ref("");
const router = useRouter();

const onLogin = async () => {
  // Send a POST request
  console.log("Start");
  const response = await axios({
    method: "post",
    url: "http://localhost:3000/login",
    data: {
      username: username.value,
      password: password.value,
    },
  });

  console.log(response);

  // auth.login(username.value);
  // router.push("/");
};
</script>
<template>
  <div>
    <h1>Login Page</h1>
    <div class="flex flex-col gap-2">
      <input
        type="text"
        v-model="username"
        class="border p-3"
        placeholder="Username"
      />
      <input
        type="text"
        v-model="password"
        class="border p-3"
        placeholder="Pass"
      />
      <button @click="onLogin()" class="bg-blue-500 text-white py-1 px-3">
        Login
      </button>
    </div>
  </div>
</template>
