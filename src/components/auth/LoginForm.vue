<template>
  <div class="wrapper" style="text-align: center">
    <div class="title">
      <q-icon name="ti-heart" color="white" size="35px" />
      Clothes 4You
    </div>
    <form @submit.prevent="login">
      <div class="field">
        <input v-model="username" type="text" required />
        <label>User</label>
      </div>
      <div class="field">
        <input v-model="password" type="password" required />
        <label>Password</label>
      </div>
      <div class="content">
        <div class="checkbox">
          <input type="checkbox" id="remember-me" />
          <label for="remember-me">Remember me</label>
        </div>
        <div class="pass-link">
          <a href="#">Forgot password?</a>
        </div>
      </div>
      <div class="field">
        <q-btn label="Login" type="submit" color="red" class="custom-btn" />
      </div>
      <div class="signup-link">Not a member? <a href="#">Signup now</a></div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      // Validar los campos de usuario y contraseña antes de enviar
      if (this.username.trim() === "" || this.password.trim() === "") {
        alert("Por favor completa los campos de usuario y contraseña.");
        return;
      }

      // Aquí puedes agregar la lógica para enviar el formulario
      console.log("Username:", this.username);
      console.log("Password:", this.password);

      // Simular redirección después de iniciar sesión
      window.location.href = "http://localhost:9000/#/sales";
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Poppins:400,500,600,700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
html,
body {
  display: grid;
  height: 100%;
  width: 100%;
  place-items: center;
  background: #f2f2f2;
  /* background: linear-gradient(-135deg, #c850c0, #4158d0); */
}
::selection {
  background: red;
  color: #fff;
}
.wrapper {
  width: 380px;
  background: #fff;
  border-radius: 15px;
  box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.1);
  text-align: center;
  align-items: center;
}
.wrapper .title {
  font-size: 35px;
  font-weight: 600;
  text-align: center;
  line-height: 100px;
  color: #fff;
  user-select: none;
  border-radius: 15px 15px 0 0;
  background: linear-gradient(-135deg, #c85050, red);
}
.wrapper form {
  padding: 10px 30px 50px 30px;
}
.wrapper form .field {
  height: 50px;
  width: 100%;
  margin-top: 20px;
  position: relative;
}
.wrapper form .field input {
  height: 100%;
  width: 100%;
  outline: none;
  font-size: 17px;
  padding-left: 20px;
  border: 1px solid lightgrey;
  border-radius: 25px;
  transition: all 0.3s ease;
}
.wrapper form .field input:focus,
form .field input:valid {
  border-color: #d09741;
}
.wrapper form .field label {
  position: absolute;
  top: 50%;
  left: 20px;
  color: #999999;
  font-weight: 400;
  font-size: 17px;
  pointer-events: none;
  transform: translateY(-50%);
  transition: all 0.3s ease;
}
form .field input:focus ~ label,
form .field input:valid ~ label {
  top: 0%;
  font-size: 16px;
  color: #4158d0;
  background: #fff;
  transform: translateY(-50%);
}
form .content {
  display: flex;
  width: 100%;
  height: 50px;
  font-size: 16px;
  align-items: center;
  justify-content: space-around;
}
form .content .checkbox {
  display: flex;
  align-items: center;
  justify-content: center;
}
form .content input {
  width: 15px;
  height: 15px;
  background: red;
}
form .content label {
  color: #262626;
  user-select: none;
  padding-left: 5px;
}
form .content .pass-link {
  color: "";
}
form .field input[type="submit"] {
  color: #fff;
  border: none;
  padding-left: 0;
  margin-top: -10px;
  font-size: 20px;
  font-weight: 500;
  cursor: pointer;
  background: linear-gradient(-135deg, #c85050, red);
  transition: all 0.3s ease;
}
form .field input[type="submit"]:active {
  transform: scale(0.95);
}
form .signup-link {
  color: #262626;
  margin-top: 20px;
  text-align: center;
}
form .pass-link a,
form .signup-link a {
  color: #4158d0;
  text-decoration: none;
}
form .pass-link a:hover,
form .signup-link a:hover {
  text-decoration: underline;
}

.custom-btn {
  color: #fff;
  border: none;
  padding-left: 0;
  margin-top: -10px;
  font-size: 20px;
  font-weight: 500;
  cursor: pointer;
  background-color: rgb(227, 17, 17);
  transition: all 0.3s ease;
  border-radius: 25px;
  width: 90%;
  height: auto;
}

.custom-btn:active {
  transform: scale(0.95);
}
</style>
