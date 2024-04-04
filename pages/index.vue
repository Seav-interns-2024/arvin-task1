<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    handleLogin(){
      this.$router.push('/home');
    },
    sendOtp() {
      alert('OTP has been sent!');
    },
    forgotPassword() {
      alert('Account Recovery sent to your email')
    }
  }
}
</script>

<template>
  <div class="flex justify-center items-center h-screen">
    <div class="w-full md:w-1/2 flex justify-center">
      <img src="/assets/images/thousandSunny.png" class="h-13 w-auto" alt="Main Logo">
    </div>
    <div class="w-full md:w-1/2 flex justify-center" id="component">
      <div class="login-container bg-gray-200 p-4 md:p-8 rounded-lg">
        <form @submit.prevent="handleLogin">
          <label class="text-sm md:text-base">Email</label>
          <input type="email" required class="block border rounded-md w-full px-2 py-1 mb-2 text-sm md:text-base">
          <label class="text-sm md:text-base">Password</label>
          <input type="password" required class="block border rounded-md w-full px-2 py-1 mb-2 text-sm md:text-base">
          <div class="flex justify-between">
            <button @click="sendOtp" class="text-sm md:text-base text-yellow-600">Send OTP</button>
            <button @click="forgotPassword" class="text-sm md:text-base text-yellow-600">Forgot Password</button>
          </div>
          <div class="flex justify-center items-center mt-4">
            <button class="block border border-yellow-600 rounded-md w-full px-2 py-1 mb-2 text-yellow-600 text-sm md:text-base hover:bg-yellow-600 hover:text-white transition-colors">
              LOG IN
            </button>
          </div>
          <div class="flex justify-between">
            <label class="text-sm md:text-base">Don't have an account yet?</label>
            <NuxtLink to="signup" class="text-sm md:text-base text-yellow-600">Sign Up</NuxtLink>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
@media screen and (max-width: 768px) {
  .flex {
    flex-direction: column;
    /* Change flex direction to column on smaller screens */
    justify-content: center;
    /* Center items vertically */
    align-items: center;
    /* Center items horizontally */
  }

  .w-full {
    width: 100%;
    /* Set width to 100% on smaller screens */
  }

  .login-container {
    padding: 40px;
  }
}

.login-container {
  width: 90%;
  /* Set width to 90% of the container */
  max-width: 500px;
  /* Set maximum width to 500px */
  height: auto;
  /* Allow height to adjust based on content */
  padding: 20px;
  /* Increase padding for better spacing */
}
</style>