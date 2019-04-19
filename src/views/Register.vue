<template>
<div>
  <div id="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/login" class="signInFront" id="signinButton">
      <svg class="circle">
        <circle cx="50%" cy="50%" r="9vh"></circle>
      </svg>
      SIGN IN
    </router-link>
    <router-link to="/register" class="signUpFront" id="signupButton">
      <svg class="circle">
        <circle cx="50%" cy="50%" r="9vh"></circle>
      </svg>
      SIGN UP
    </router-link>
  </div>
  <h1>Register for an account</h1>
  <form @submit.prevent="register" class="pure-form pure-form-aligned">
    <fieldset>
      <p class="pure-form-message-inline">All fields are required.</p>

      <div class="pure-control-group">
        <label for="firstName">First Name</label>
        <input v-model="firstName" type="text" placeholder="First Name">
      </div>

      <div class="pure-control-group">
        <label for="lastName">Last Name</label>
        <input v-model="lastName" type="text" placeholder="Last Name">
      </div>

      <div class="pure-control-group">
        <label for="username">Username</label>
        <input v-model="username" type="text" placeholder="Username">
      </div>

      <div class="pure-control-group">
        <label for="password">Password</label>
        <input v-model="password" type="password" placeholder="Password">
      </div>

      <div class="pure-control-group">
        <label for="minutesRead">Number of minutes read already</label>
        <input v-model="minutesRead" type="text" placeholder="Username">
      </div>

      <div class="pure-control-group">
        <label for="grade">Grade</label>
        <input v-model="grade" type="text" placeholder="Username">
      </div>

      <div class="pure-control-group">
        <label for="email">E-Mail</label>
        <input v-model="email" type="text" placeholder="Username">
      </div>

      <div class="pure-controls">
        <button type="submit" class="submit">Submit</button>
      </div>
    </fieldset>
  </form>
  <p v-if="error" class="error">{{error}}</p>
</div>
</template>

<script>
export default {
  name: 'register',
  data() {
    return {
      firstName: '',
      lastName: '',
      username: '',
      password: '',
      minutesRead: '',
      grade: '',
      email: '',
      error: '',
    }
  },
  methods: {
    async register() {
      try {
        this.error = await this.$store.dispatch("register", {
          firstName: this.firstName,
          lastName: this.lastName,
          username: this.username,
          password: this.password,
          minutesRead: this.minutesRead,
          grade: this.grade,
          email: this.email,
        });
        if (this.error === "")
          this.$router.push('/login');
      } catch (error) {
        console.log(error);
      }
    }
  }
}
</script>

<style scoped>
form {
  font-family: sans-serif;
  background-color: #c7f65a;
  border-radius: 7px;
  padding: 20px;
  position: relative;
  top: 20vh;
  width: 30vw;
  left: 33vw;
}

.submit{
  text-align: center;
  background-color: white;
  border-style: solid;
  border-color: #c64d56;
  border-radius: 7px;
  padding: 10px;
  margin: 10px;
  width: 50%;
}
</style>
