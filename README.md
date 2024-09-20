# Componente de Autenticación en Svelte

Este proyecto proporciona un componente de autenticación desarrollado con **Svelte** que incluye validación de correo electrónico y contraseña.

## Contenido

1. (#descripción)
2. (#características)
3. (#uso)
4. (#validaciones-implementadas)
5. (#funciones)
   - (#validar-email)
   - (#validar-contraseña)
   - (#toggle-password-visibility)
   - (#recordar-usuario)

## Descripción

Este componente está diseñado para ser fácil de integrar en cualquier aplicación web desarrollada con Svelte.

## Características

- Validación de correo electrónico con expresión regular.
- Validación de contraseña que verifica:
  - Longitud (6-12 caracteres).
  - Inclusión de al menos una letra mayúscula.
  - Inclusión de al menos un número.
  - Inclusión de al menos un símbolo.
- Opción para recordar al usuario con Local Storage.
- Alternancia de visibilidad de la contraseña.

# Uso

Se importa el componente de autenticación en la aplicación Svelte.

<script>
  import AuthComponent from './AuthComponent.svelte';
</script>

<AuthComponent />

# Validaciones Implementadas

## Validar Email

El correo electrónico se valida asegurandoce de que esté en un formato sea válido (por ejemplo, usuario@dominio.com).

## Validar Contraseña

En la contraseña debe cumplir con las siguientes caracteristicas:

Al menos 6 caracteres y no más de 12.
Contener al menos una letra mayúscula.
Contener al menos un número.
Contener al menos un símbolo especia

# Funciones

## Validar Email

Valida el formato del correo electrónico y muestra un mensaje de error si es inválido.

<script>

function validarEMail() {
  const emailPattern = /^[a-z0-9]+@[a-z]+\.[a-z]{2,3}$/;
  if (!email) {
    errorMail = 'Debes introducir un mail';
    return false;
  } else if (!emailPattern.test(email)) {
    errorMail = 'El mail debe de ser válido';
    return false;
  }
  errorMail = '';
  return true;
}

</script>


# Validar Contraseña

se realiza la comprobacion de que la contraseña cumpla los requisitos.

<script>
function validarContrasinal() {
  const regexNumero = /[0-9]/;
  const regexMayus = /[A-Z]/;
  const regexSimbolo = /\W/;

  if (!password) {
    errorPassword = 'Debes introducir una contraseña';
    return false;
  } else if (!password.match(regexMayus) || !password.match(regexNumero) || !password.match(regexSimbolo)) {
    if (!regexMayus.test(password)) {
      errorPassword = 'La contraseña debe tener al menos una mayúscula';
    } else if (!regexNumero.test(password)) {
      errorPassword = 'La contraseña debe tener al menos un número';
    } else if (!regexSimbolo.test(password)) {
      errorPassword = 'La contraseña debe tener al menos un símbolo';
    }
    return false;
  } else if (password.length < 6 || password.length > 12) {
    errorPassword = 'La contraseña debe tener entre 6 y 12 caracteres';
    return false;
  }
  errorPassword = '';
  return true;
}
</script>


# Toggle Password Visibility

Se alterna la visibilidad de la contraseña.

<script>

function togglePasswordVisibility() {
  showPassword = !showPassword;
}
Recordar Usuario
Utiliza Local Storage para recordar el correo electrónico del usuario si selecciona la opción "Recordar mi correo".

svelte
Copiar código
onMount(() => {
  const storedEmail = localStorage.getItem('mail');
  if (storedEmail) {
    email = storedEmail;
  }
});

</script>

