<script>
  import { fade } from 'svelte/transition';
</script>

<section class="relative bg-gradient-to-r from-[#3F7D20]/10 to-white">
  <div class="container mx-auto px-4 py-16 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <!-- Text Content -->
      <div class="space-y-8" in:fade={{ duration: 500 }}>
        <div class="space-y-2">
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-[#3F7D20] leading-tight">
            Valsalya Speciality Clinic
          </h1>
          <p class="text-xl sm:text-2xl text-gray-600 italic">
            Where Compassion Meets Excellence
          </p>
        </div>
        <p class="text-lg sm:text-xl text-gray-600 max-w-2xl">
          Welcome to Valsalya Speciality Clinic, your trusted healthcare partner. Our state-of-the-art facility combines cutting-edge medical technology with compassionate care. Led by experienced specialists and supported by a dedicated team of healthcare professionals, we are committed to providing personalized treatment plans and comprehensive care for all your medical needs.
        </p>
        <div class="flex gap-4">
          <a href="/appointment" class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-white bg-[#3F7D20] hover:bg-[#2E5D17] transition-colors duration-200">
            Book Appointment
          </a>
          <a href="/services" class="inline-flex items-center px-6 py-3 border border-[#3F7D20] text-base font-medium rounded-md text-[#3F7D20] hover:bg-[#3F7D20]/10 transition-colors duration-200">
            Our Services
          </a>
        </div>
      </div>

      <!-- Image -->
      <div class="relative h-[400px] lg:h-[500px] rounded-lg overflow-hidden shadow-xl" in:fade={{ duration: 500, delay: 200 }}>
        <img
          src="https://images.unsplash.com/photo-1579684385127-1ef15d508118?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80"
          alt="Modern medical clinic interior"
          class="absolute inset-0 w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gradient-to-r from-[#3F7D20]/20 to-transparent"></div>
      </div>
    </div>
  </div>

  <!-- Decorative Elements -->
  <div class="absolute bottom-0 left-0 right-0 h-16 bg-gradient-to-t from-white to-transparent"></div>
</section>

<style>
  /* Add any custom styles here if needed */
</style> 