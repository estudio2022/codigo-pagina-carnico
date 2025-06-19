<template>
  <div class="login-container">
    <h2>Iniciar Sesión</h2>
    <form @submit.prevent="login">
      <input v-model="email" type="text" placeholder="Usuario o Correo Electronico" required />
      <input v-model="password" type="password" placeholder="Contraseña" required />
      <button type="submit">Iniciar Sesión</button>
    </form>
    <div v-if="error" class="error">{{ error }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      error: null,
    };
  },
  methods: {
    async login() {
      // Aquí llamaría a tu API Laravel (endpoint /login)
      try {
        // Simulación de respuesta
        if (this.email === "admin" && this.password === "admin") {
          alert("Login exitoso");
        } else {
          this.error = "Credenciales inválidas";
        }
      } catch {
        this.error = "Error de conexión";
      }
    }
  }
};
</script>

<style>
.login-container { max-width: 400px; margin: 50px auto; padding: 2rem; background: #fff; border-radius: 15px; }
input { display: block; width: 100%; margin-bottom: 10px; }
button { width: 100%; padding: 10px; background: #3b55c6; color: #fff; border: none; border-radius: 8px; }
.error { color: red; }
</style>
