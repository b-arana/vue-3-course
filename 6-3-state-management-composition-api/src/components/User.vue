<template>
  <template v-if="isLogged">
    <img :src="user.image" :alt="user.name" class="avatar" />
    <button @click="logout" class="button button--default">Logout</button>
  </template>
  <button v-else @click="login" class="button button--primary">
    Log in
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { useUser } from "@/use/user";

export default defineComponent({
  setup() {
    const { user, isLogged, login, logout } = useUser();

    return {
      user,
      isLogged,
      login,
      logout,
    };
  },
});
</script>

<style scoped>
.button {
  padding: 0.5rem 1rem;
  border: 3px solid;
  border-radius: 0.2rem;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 700;
}
.button--primary {
  background: #10fb7a;
  border-color: #10fb7a;
  color: #333;
}
.button--default {
  background: #333;
  color: #10fb7a;
}
.avatar {
  border-radius: 50%;
  max-height: 2.65rem;
  margin-right: 1rem;
}
</style>
