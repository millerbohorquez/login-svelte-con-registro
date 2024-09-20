<script>
  let nombre = '';
  let apellido = '';
  let email = '';
  let password = '';
  let confirmPassword = '';
  let errorMail = '';
  let errorPassword = '';
  let errorConfirmPassword = '';

  function validarEMail() {
    const emailPattern = /^[a-z0-9]+@[a-z]+\.[a-z]{2,3}$/;
    if (!email) {
      errorMail = 'Debes introducir un correo';
      return false;
    } else if (!emailPattern.test(email)) {
      errorMail = 'El correo debe ser válido';
      return false;
    }
    errorMail = '';
    return true;
  }

  function validarPassword() {
    if (password !== confirmPassword) {
      errorConfirmPassword = 'Las contraseñas no coinciden';
      return false;
    }
    errorConfirmPassword = '';
    return true;
  }

  function validar(event) {
    event.preventDefault();
    if (validarEMail() && validarPassword()) {
      alert('Registro exitoso');
      window.location.href = '/login'; // Redirige al login tras registrarse
    }
  }
</script>

<style>
  .main-container {
 background-image: url('https://linktic.com/media/2024/03/logo-footer.svg');
 background-size: cover;
 width: 35%;
 height: 97vh;

 
}

.right {
 position: absolute;
 width: 360px;
 left: 38%;
 height: 650px;
 top: calc(50% - 580px / 2);
 background: #f2f8ff;
 border-radius: 25px;
 text-align: center;
}

.title {
 font-style: normal;
 font-weight: bold;
 font-size: 25px;
 line-height: 145px;
 align-items: center;
 font-family: "Open Sans", sans-serif;
 color: #04132a;
}

.title .fa-brands {
 font-size: 15px;
 margin: 0 10px;
}

.title .fa-brands:nth-child(2) {
 transform: rotateY(180deg);
}

.fa-dove {
 font-size: 70px;
 margin-top: -30px;
 color: #04132a;
}
label .fa-envelope{
  font-size: 20px;
 position: absolute;
 padding: 24px 32px;
 margin-left: 7px;
 margin-top: -6px;
 color: #04132a ;
}

form {
 margin-top: 50px;
}

input[type="email"],
input[type="password"],
input[type="text"] {
 border: none;
 outline: none;
 background: none;
 font-size: 14px;
 color: black;
 padding: 20px 10px 20px 5px;
 border: 2px solid #636363;
 width: 280px;
 height: 45px;
 margin: 5px 15px;
 border-radius: 25px;
 box-sizing: border-box;
 text-align: center;
 overflow: hidden;
 font-family: "Nunito Sans", sans-serif;
}

input[type="email"]:hover{
 border: 2px solid #5C8BFF;
 cursor: pointer;
}
input[type="text"]:hover{
 border: 2px solid #5C8BFF;
 cursor: pointer;
}
input[type="password"]:hover{
 border: 2px solid #5C8BFF;
 cursor: pointer;
}

.contra {
 margin-bottom: 50px;
}

.errorMensajeForm{
 margin-bottom: 20px;
}

::placeholder {
 color: #9D9EA2;
 font-size: 18px;
}

label .fa-user{
 font-size: 20px;
 position: absolute;
 padding: 24px 32px;
 margin-top: -5px;
 margin-left: 5px;
 color: #04132a;
 
}

label .fa-lock {
 font-size: 20px;
 position: absolute;
 padding: 24px 32px;
 margin-left: 7px;
 margin-top: -6px;
 color: #04132a ;
}

.keepme {
 color:black;
 font-family: "Nunito Sans", sans-serif;
}

label .fa-regular {
 font-size: 15px;
 position: absolute;
 padding: 25px 0px;
 margin-left: -60px;
 margin-top: -6px;
 color: #04132a;
}

label i.fa-eye {
 color:#0049ff;
}

input[type="checkbox"] {
 vertical-align: middle;
 margin: 30px 3px;
 font-weight: bold;
 height: 18px;
 width: 18px;
 cursor: pointer;
}

button {
 width: 260px;
 height: 45px;
 left: 1273px;
 top: 780px;
 margin: 0px 20px 20px;
 font-weight: bold;
 font-size: 20px;
 line-height: 28px;
 cursor: pointer;
 color: #E0E0E0;
 border: none;
 background: #0049ff;
 border-radius: 25px;
 
}

button:hover {
 background: #5C8BFF;
 width: 230px;
 height: 43px;
 transition: all .3s;
 transition-duration: 0.3s;

}

.link {
 text-align: center;
 display: block;
 margin: 0 18px;
 color: #e6f6ff;
 font-family: "Nunito Sans", sans-serif;
 font-size: 15px;
}

.link a {
 color: #e6f6ff;
 font-weight: bold;
}

footer {
 flex-shrink: 0;
 background-color: black;
 color: rgb(240, 239, 239);
 box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.2);
 border-top: 1px solid #5695cf;
 width: 100%;
 height: 20px;
 text-align: center;
 padding-bottom: 7px;
}

small {
 font-family: "Nunito Sans", sans-serif;
 font-weight: bold;
 font-size: 12px;
}

small > a {
 color: #fff;
 font-size: 11px;
}


.error {
 border: solid 2px rgb(253, 29, 29);
}

.mensajeError {
 color: rgb(255, 47, 47);
 font-size: smaller;
 font-weight: bold;
 font-family: 'Times New Roman', Times, serif;
}

.normal {
 font-size: normal;
 font-weight: normal;
}


@media only screen and (max-width: 900px) {
 .main-container {
   background: linear-gradient(138.56deg, #5695cf 23.44%, #88183a 89.5%);
 }

 .right {
   left: calc(68% - 500px / 2);
  
 }
}

</style>

<main class="main-container">
  <section class="right">
    <h1 class="title">
      <i class="fa-brands fa-itunes-note"></i> Sign Up
      <i class="fa-brands fa-itunes-note"></i>
    </h1>
    <i class="fa-solid fa-dove"></i>
    <form class="form-container" on:submit={validar}>
      <label for="nombre">
        <i class="fa-solid fa-user"></i>
        <input type="text" placeholder="Name" bind:value={nombre} required />
      </label>
      <div id="contra">
        <label for="apellido">
          <i class="fa-solid fa-user"></i>
          <input type="text" placeholder="Last Name" bind:value={nombre} required />
        </label>
      </div>
      <div id="contra">
        <label for="mail">
          <i class="fa-solid fa-envelope"></i>
          <input  type="email"  placeholder="E-Mail"  bind:value={email}  on:input={() => errorMail = ''}  required/>
          {#if errorMail}
            <p id="errorMail" class="errorMensajeForm">{errorMail}</p>
          {/if}
        </label>
      </div>
      <div id="contra">
        <label for="password">
          <i class="fa-solid fa-lock"></i>
          <input type="password" placeholder="Password" bind:value={password} required />
        </label>
      </div>
      <div id="contra">
        <label for="password">
          <i class="fa-solid fa-lock"></i>
          <input type="password" placeholder="Confirm Password" bind:value={confirmPassword} required />
          {#if errorConfirmPassword}
            <p>{errorConfirmPassword}</p>
          {/if}
        </label>
      </div>
      <br>
      <button type="submit" id="enviar">Register</button>
    </form>
  </section>
</main>
