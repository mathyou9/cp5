<template>
  <div class="home">
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
    <HomeComponent/>
  </div>
</template>


<script>
// @ is an alias to /src
import HomeComponent from '@/components/HomeComponent.vue'

export default {
  name: 'home',
  components: {
    HomeComponent
  }
}
</script>
