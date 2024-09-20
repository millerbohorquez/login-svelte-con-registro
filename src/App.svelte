<script>
  import LoginForm from './Login.svelte';
  import RegisterForm from './Register.svelte';

  let showRegister = false;

  function toggleForm() {
    showRegister = !showRegister;
  }
</script>

<main>
  {#if showRegister}
    <RegisterForm />
    <strong>¿Ya tienes cuenta? <a href="#" on:click|preventDefault={toggleForm}>Inicia sesión aquí</a></strong>
  {:else}
    <LoginForm />
    <strong>¿No tienes cuenta? <a href="#" on:click|preventDefault={toggleForm}>Regístrate aquí</a></strong>
  {/if}
</main>
