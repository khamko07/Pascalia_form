<template>
  <div class="form-container">
    <form @submit.prevent="handleSubmit" class="register-form" v-if="showRegister">
      <h1>Register</h1>
      <img :src="require('./assets/img/pav-1.png')" alt="Company Logo" class="logo">
      
      <div class="form-group">
        <label for="fullName">Full Name</label>
        <input type="text" id="fullName" v-model="form.fullName" required>
      </div>

      <div class="form-group">
        <label for="dob">Date of Birth</label>
        <input type="date" id="dob" v-model="form.dob" required>
      </div>

      <div class="form-group">
        <label>Gender</label>
        <div class="radio-group">
          <input type="radio" id="male" value="male" v-model="form.gender">
          <label for="male">Male</label>
          <input type="radio" id="female" value="female" v-model="form.gender">
          <label for="female">Female</label>
        </div>
      </div>

      <div class="form-group">
        <label for="address">Address</label>
        <textarea id="address" v-model="form.address" required></textarea>
      </div>

      <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" v-model="form.phone" required>
      </div>

      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" v-model="form.email" required>
      </div>

      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" v-model="form.password" required>
      </div>

      <div class="form-group">
        <label for="confirmPassword">Confirm Password</label>
        <input type="password" id="confirmPassword" v-model="form.confirmPassword" required>
      </div>

      <button type="submit">Register</button>
      
      <p class="switch-form">
        Already have an account? 
        <a href="#" @click.prevent="toggleForm">Login here</a>
      </p>
      
      <div class="copyright">
        © 2024 Pascalia Group Co., Ltd. All rights reserved.
      </div>
    </form>

    <form @submit.prevent="handleLogin" class="login-form" v-else>
      <h1>Login</h1>
      <img src="@/assets/img/pav-1.png" alt="Company Logo" class="logo">
      
      <div class="form-group">
        <label for="loginEmail">Email Address</label>
        <input type="email" id="loginEmail" v-model="loginForm.email" required>
      </div>

      <div class="form-group">
        <label for="loginPassword">Password</label>
        <input type="password" id="loginPassword" v-model="loginForm.password" required>
      </div>

      <button type="submit">Login</button>
      
      <p class="switch-form">
        Don't have an account? 
        <a href="#" @click.prevent="toggleForm">Register here</a>
      </p>
      
      <div class="copyright">
        © 2024 Pascalia Group Co., Ltd. All rights reserved.
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'UserRegister',
  data() {
    return {
      showRegister: true,
      form: {
        fullName: '',
        dob: '',
        gender: '',
        address: '',
        phone: '',
        email: '',
        password: '',
        confirmPassword: ''
      },
      loginForm: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    toggleForm() {
      this.showRegister = !this.showRegister
    },
    handleSubmit() {

      console.log('Registration form submitted:', this.form)
    },
    handleLogin() {
      console.log('Login form submitted:', this.loginForm)
    }
  }
}
</script>

<style scoped>
.form-container {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
}

.register-form, .login-form {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #060303;
  margin-bottom: 20px;
}

.logo {
  display: block;
  margin: 0 auto 20px;
  max-width: 150px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  color: #140f0f;
}

input, textarea {
  width: 100%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
}

.radio-group {
  display: flex;
  gap: 20px;
}

.radio-group input[type="radio"] {
  width: auto;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #1cd8ed;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 10px;
}

button:hover {
  background-color: #1acded;
}

.switch-form {
  text-align: center;
  margin-top: 15px;
}

.switch-form a {
  color: #0e0f0e;
  text-decoration: none;
}

.switch-form a:hover {
  text-decoration: underline;
}

.copyright {
  text-align: center;
  color: #0c0c0c;
  font-size: 14px;
  margin-top: 20px;
  padding-bottom: 10px;
}
</style>