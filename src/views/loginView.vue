<template>
  <v-app>
    <v-container class="d-flex justify-center align-center" style="height: 100vh">
      <v-card width="400" class="pa-5">
        <v-card-title class="text-h5 text-center"> Simple Authentication </v-card-title>
        <v-card-text>
          <v-form>
            <!-- Email Field -->
            <v-text-field
              v-model="email"
              label="Email"
              type="email"
              required
              :rules="[emailRule]"
            ></v-text-field>

            <!-- Password Field -->
            <v-text-field
              v-model="password"
              label="Password"
              type="password"
              required
              :rules="[passwordRule]"
            ></v-text-field>

            <!-- Buttons -->
            <div class="mt-4">
              <v-btn block color="primary" @click="handleLogin"> Log In </v-btn>
              <v-btn block color="secondary" @click="handleSignUp" class="mt-2"> Sign Up </v-btn>
            </div>
          </v-form>
        </v-card-text>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      emailRule: (value) => !!value || 'Email is required',
      passwordRule: (value) =>
        (value && value.length >= 6) || 'Password must be at least 6 characters',
    }
  },
  methods: {
    handleLogin() {
      if (!this.email || !this.password) {
        alert('Please fill in all fields.')
        return
      }
      // Mock login logic
      console.log('Logging in with:', this.email, this.password)
      alert('Logged in successfully!')
    },
    handleSignUp() {
      if (!this.email || !this.password) {
        alert('Please fill in all fields.')
        return
      }
      // Mock signup logic
      console.log('Signing up with:', this.email, this.password)
      alert('Signed up successfully!')
    },
  },
}
</script>

<style>
body {
  margin: 0;
  font-family: Roboto, sans-serif;
}
</style>
