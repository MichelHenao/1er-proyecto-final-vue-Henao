<template>
    <div class="container">
      <div class="row">
        <div class="col-md-6 col-md-offset-3">
          <div class="panel panel-login">
            <div class="panel-heading">
              <div class="row">
                <div class="col-xs-6">
                  <a href="#" :class="{ 'active': showLoginForm }" @click="showLoginForm = true; showRegisterForm = false">Login</a>
                </div>
                <div class="col-xs-6">
                  <a href="#" :class="{ 'active': showRegisterForm }" @click="showLoginForm = false; showRegisterForm = true">Register</a>
                </div>
              </div>
              <hr>
            </div>
            <div class="panel-body">
              <div class="row">
                <div class="col-lg-12">
                  <form id="login-form" @submit.prevent="login" v-show="showLoginForm">
                    <div class="form-group">
                      <input type="text" v-model="loginForm.username" class="form-control" placeholder="Username">
                    </div>
                    <div class="form-group">
                      <input type="password" v-model="loginForm.password" class="form-control" placeholder="Password">
                    </div>
                    <div class="form-group text-center">
                      <input type="checkbox" v-model="loginForm.remember" class="" id="remember">
                      <label for="remember">Remember Me</label>
                    </div>
                    <div class="form-group">
                      <div class="row">
                        <div class="col-sm-6 col-sm-offset-3">
                          <button type="submit" class="form-control btn btn-login" :disabled="isLoggingIn">Log In</button>
                        </div>
                      </div>
                    </div>
                  </form>
                  <form id="register-form" @submit.prevent="register" v-show="showRegisterForm">
                    <div class="form-group">
                      <input type="text" v-model="registerForm.username" class="form-control" placeholder="Username">
                    </div>
                    <div class="form-group">
                      <input type="email" v-model="registerForm.email" class="form-control" placeholder="Email Address">
                    </div>
                    <div class="form-group">
                      <input type="password" v-model="registerForm.password" class="form-control" placeholder="Password">
                    </div>
                    <div class="form-group">
                      <input type="password" v-model="registerForm.confirmPassword" class="form-control" placeholder="Confirm Password">
                    </div>
                    <div class="form-group">
                      <div class="row">
                        <div class="col-sm-6 col-sm-offset-3">
                          <button type="submit" class="form-control btn btn-register" :disabled="isRegistering">Register Now</button>
                        </div>
                      </div>
                    </div>
                  </form>
                  <div v-if="loginError" class="alert alert-danger">
                    {{ loginError }}
                  </div>
                  <div v-if="registrationSuccess" class="alert alert-success">
                    Your account has been registered successfully. Please log in.
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
     </div>
  </div>
</template>
        
  

<script>
export default {
name:"LoginComponent",
data() {
    return {
      showLoginForm: true,
      showRegisterForm: false,
      loginForm: {
        username: '',
        password: '',
        remember: false
      },
      registerForm: {
        username: '',
        email: '',
        password: '',
        confirmPassword: ''
      },
      isLoggingIn: false,
      isRegistering: false,
      loginError: null,
      registrationSuccess: false
    };
  },
  methods: {
    login() {
      this.isLoggingIn = true;

      // Simula una solicitud de autenticación después de 1 segundo
      setTimeout(() => {
        const { username, password } = this.loginForm;
        const user = this.users.find((u) => u.username === username && u.password === password);

        if (user) {
          this.isLoggingIn = false;
          this.loginError = null;
          // Realiza la redirección a la página de inicio o realiza otra acción necesaria
          this.$router.push("/home");
        } else {
          this.isLoggingIn = false;
          this.loginError = "Invalid or non-existent user";
        }
      }, 1000);
    },
    register() {
      this.isRegistering = true;

      // Simula una solicitud de registro después de 1 segundo
      setTimeout(() => {
        this.isRegistering = false;
        this.registrationSuccess = true;
        this.showLoginForm = true;
        this.showRegisterForm = false;
      }, 1000);
    },
  },
};
</script>


<style scoped>
body {
    padding-top: 90px;
}
.panel-login {
	border-color: #ccc;
	-webkit-box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
	-moz-box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
	box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
}
.panel-login>.panel-heading {
	color: #00415d;
	background-color: #fff;
	border-color: #fff;
	text-align:center;
}
.panel-login>.panel-heading a{
	text-decoration: none;
	color: #666;
	font-weight: bold;
	font-size: 15px;
	-webkit-transition: all 0.1s linear;
	-moz-transition: all 0.1s linear;
	transition: all 0.1s linear;
}
.panel-login>.panel-heading a.active{
	color: #029f5b;
	font-size: 18px;
}
.panel-login>.panel-heading hr{
	margin-top: 10px;
	margin-bottom: 0px;
	clear: both;
	border: 0;
	height: 1px;
	background-image: -webkit-linear-gradient(left,rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.15),rgba(0, 0, 0, 0));
	background-image: -moz-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
	background-image: -ms-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
	background-image: -o-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
}
.panel-login input[type="text"],.panel-login input[type="email"],.panel-login input[type="password"] {
	height: 45px;
	border: 1px solid #ddd;
	font-size: 16px;
	-webkit-transition: all 0.1s linear;
	-moz-transition: all 0.1s linear;
	transition: all 0.1s linear;
}
.panel-login input:hover,
.panel-login input:focus {
	outline:none;
	-webkit-box-shadow: none;
	-moz-box-shadow: none;
	box-shadow: none;
	border-color: #ccc;
}
.btn-login {
	background-color: #59B2E0;
	outline: none;
	color: #fff;
	font-size: 14px;
	height: auto;
	font-weight: normal;
	padding: 14px 0;
	text-transform: uppercase;
	border-color: #59B2E6;
}
.btn-login:hover,
.btn-login:focus {
	color: #fff;
	background-color: #53A3CD;
	border-color: #53A3CD;
}
.forgot-password {
	text-decoration: underline;
	color: #888;
}
.forgot-password:hover,
.forgot-password:focus {
	text-decoration: underline;
	color: #666;
}

.btn-register {
	background-color: #1CB94E;
	outline: none;
	color: #fff;
	font-size: 14px;
	height: auto;
	font-weight: normal;
	padding: 14px 0;
	text-transform: uppercase;
	border-color: #1CB94A;
}
.btn-register:hover,
.btn-register:focus {
	color: #fff;
	background-color: #1CA347;
	border-color: #1CA347;
}
</style>