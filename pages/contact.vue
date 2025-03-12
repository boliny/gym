<template>
  <section class="bg-cream py-16 px-6 md:px-12">
    <div class="max-w-3xl mx-auto text-center">
      <p class="text-sm font-semibold text-gray-600">READY TO START?</p>
      <h2 class="text-3xl font-bold text-gray-900 mt-2">CONTACT ME</h2>
    </div>
    <div class="mt-10 flex flex-col md:flex-row justify-center items-center gap-8">
      <div class="text-center md:text-left">
        <div class="flex items-center justify-center md:justify-start gap-2">
          
          <p class="text-gray-700">The Company Name Inc.</p>
        </div>
        <p class="text-gray-600">8901 Marmora Road,<br />Glasgow, D04 89GR.</p>
      </div>
      <div class="text-center md:text-left">
        <div class="flex items-center justify-center md:justify-start gap-2">
         
          <p class="text-gray-700">+1 800 559 6580</p>
        </div>
        <p class="text-gray-600">+1 800 889 9898<br />mail@demolink.org</p>
      </div>
    </div>
    <div class="mt-12 max-w-3xl mx-auto">
      <p class="text-center font-semibold text-gray-700 mb-4">OR JUST DROP ME A LINE</p>
      <form @submit.prevent="submitForm" class="space-y-4">
        <div class="flex flex-col md:flex-row gap-4">
          <input v-model="form.name" type="text" placeholder="NAME" class="input-field" required />
          <input v-model="form.email" type="email" placeholder="EMAIL" class="input-field" required />
        </div>
        <textarea v-model="form.message" placeholder="MESSAGE" class="input-field h-32" required></textarea>
        <button type="submit" class="bg-black text-white px-6 py-2 rounded-md">Send Message</button>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const form = ref({ name: '', email: '', message: '' });

const submitForm = () => {
  alert(`Message Sent!\nName: ${form.value.name}\nEmail: ${form.value.email}\nMessage: ${form.value.message}`);
  form.value = { name: '', email: '', message: '' }; // Clear form
};
</script>

<style scoped>
.bg-cream {
  background-color: #fdfaf3;
}
.input-field {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
}
.input-field:focus {
  border-color: #000;
}
</style>
