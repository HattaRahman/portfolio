<template>
  <form @submit.prevent="handleSubmit" class="glass-card max-w-xl mx-auto p-6 rounded-2xl shadow-xl space-y-4 backdrop-blur">
    <div>
      <label class="text-white font-semibold">Name</label>
      <input
        v-model="form.name"
        type="text"
        placeholder="Your name"
        class="input"
      />
      <p v-if="errors.name" class="text-sm text-red-400">{{ errors.name }}</p>
    </div>

    <div>
      <label class="text-white font-semibold">Email</label>
      <input
        v-model="form.email"
        type="email"
        placeholder="you@example.com"
        class="input"
      />
      <p v-if="errors.email" class="text-sm text-red-400">{{ errors.email }}</p>
    </div>

    <div>
      <label class="text-white font-semibold">Message</label>
      <textarea
        v-model="form.message"
        placeholder="Let’s work together!"
        rows="5"
        class="input"
      ></textarea>
      <p v-if="errors.message" class="text-sm text-red-400">{{ errors.message }}</p>
    </div>

    <button
      type="submit"
      class="w-full py-2 px-4 bg-gradient-to-r from-purple-600 to-indigo-500 text-white font-bold rounded-lg shadow-md hover:opacity-90 transition"
    >
      Send Message
    </button>
  </form>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  message: ''
})

const errors = ref({})

const handleSubmit = () => {
  errors.value = {}

  // Basic Validation
  if (!form.name) errors.value.name = 'Name is required.'
  if (!form.email) errors.value.email = 'Email is required.'
  else if (!/\S+@\S+\.\S+/.test(form.email)) errors.value.email = 'Enter a valid email.'
  if (!form.message) errors.value.message = 'Message is required.'

  if (Object.keys(errors.value).length === 0) {
    alert('🎉 Message sent! (Not really, this is a demo 💌)')
    form.name = ''
    form.email = ''
    form.message = ''
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  padding: 0.75rem;
  border-radius: 0.5rem;
  background-color: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  font-size: 1rem;
  backdrop-filter: blur(5px);
}
.input::placeholder {
  color: rgba(255, 255, 255, 0.5);
}
.glass-card {
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(15px);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.2);
}
</style>
