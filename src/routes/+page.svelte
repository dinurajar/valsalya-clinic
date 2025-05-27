<script lang="ts">
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';

  const services = [
    {
      title: '24/7 Hospital Services',
      description: 'Our fully equipped emergency department operates round the clock, providing immediate medical attention and comprehensive care when you need it most.',
      image: 'https://images.unsplash.com/photo-1587351021759-3e566b6af7cc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80'
    },
    {
      title: '24/7 Laboratory Services',
      description: 'State-of-the-art diagnostic laboratory available 24/7. Quick and accurate test results with modern equipment and expert technicians.',
      image: '/images/laboratory.jpg'
    },
    {
      title: '24/7 Pharmacy Services',
      description: 'Full-service pharmacy open 24/7. Wide range of medications, expert consultation, and quick service for all your pharmaceutical needs.',
      image: 'https://images.unsplash.com/photo-1584308666744-24d5c474f2ae?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80'
    }
  ];

  const doctors = [
    {
      name: 'Dr. Bibin Abdul Kader',
      specialization: 'MD Internal Medicine',
      role: 'Consultant Physician & Diabetologist',
      timing: 'Tuesday & Friday 5 PM to 7 PM',
      image: '/images/bibin.png'
    },
    {
      name: 'Dr. Thouseef A Majeed',
      specialization: 'MBBS, MS Ortho',
      role: 'Consultant Orthopaedic Surgeon',
      timing: 'Monday & Thursday 5 PM to 7 PM',
      image: '/images/thouseef.png'
    },
    {
      name: 'Dr. Nabeel Ibrahim',
      specialization: 'MBBS, MD',
      role: 'Consultant Paediatrician',
      timing: 'Monday, Wednesday & Friday 3 PM to 5 PM',
      image: '/images/nabeel.png'
    }
  ];
</script>

<!-- Hero Section -->
<section class="relative h-[600px] overflow-hidden">
  <div class="absolute inset-0 bg-black/40 z-10"></div>
  <img
    src="https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80"
    alt="Valsalya Speciality Clinic"
    class="w-full h-full object-cover"
  />
  <div class="absolute inset-0 z-20 flex items-center">
    <div class="container mx-auto px-4">
      <div class="max-w-2xl text-white" in:fly={{ y: 20, duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold mb-4">Welcome to Valsalya Speciality Clinic</h1>
        <p class="text-lg md:text-xl mb-8">
          At Valsalya Speciality Clinic, we are committed to delivering compassionate, comprehensive and quality healthcare around the clock. 
          <span class="text-2xl md:text-3xl font-bold text-red-500">Operating 24/7</span>, our clinic is equipped with a fully functional casualty/emergency department, in-house pharmacy and advanced diagnostic laboratory to ensure timely and efficient medical care.
        </p>
        <a
          href="/appointment"
          class="inline-block bg-[#5CA595] text-white px-8 py-3 rounded-full font-semibold hover:bg-[#5CA595]/90 transition-colors"
        >
          Book an Appointment
        </a>
      </div>
    </div>
  </div>
</section>

<div class="bg-white">
  <!-- Services Section -->
  <section class="py-20 bg-[#5CA595]/5">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-black mb-4">Our Services</h2>
        <p class="text-lg text-black max-w-2xl mx-auto">
          Experience the difference of patient-first care in a modern, well-equipped, and friendly environment.
        </p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        {#each services as service, i}
          <div
            class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow duration-300"
            in:fade={{ duration: 500, delay: i * 100 }}
          >
            <div class="relative h-48">
              <img
                src={service.image}
                alt={service.title}
                class="w-full h-full object-cover"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold text-black mb-2">{service.title}</h3>
              <p class="text-black">{service.description}</p>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Doctors Section -->
  <section class="py-20 bg-[#5CA595]/10">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-black mb-4">Our Doctors</h2>
        <p class="text-base md:text-lg text-black max-w-6xl mx-auto leading-relaxed px-4">
          We bring together a team of experienced doctors across multiple specialities, providing expert care under one roof.
          <br class="hidden md:block">
          Whether it's a routine consultation or an urgent medical need, Valsalya is your trusted healthcare partner day or night.
        </p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        {#each doctors as doctor, i}
          <div
            class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow duration-300"
            in:fade={{ duration: 500, delay: i * 100 }}
          >
            <div class="h-48">
              <img
                src={doctor.image}
                alt={doctor.name}
                class="w-full h-full object-contain"
              />
            </div>
            <div class="p-4">
              <h3 class="text-xl font-bold text-gray-900 mb-2">{doctor.name}</h3>
              <p class="text-[#5CA595] font-medium mb-2">{doctor.specialization}</p>
              <p class="text-gray-600 mb-2">{doctor.role}</p>
              <p class="text-sm text-gray-600 mb-4">
                <span class="font-medium">Timing:</span> {doctor.timing}
              </p>
              <a
                href="/appointment"
                class="inline-flex items-center justify-center w-full px-6 py-2 text-sm font-medium text-white bg-[#5CA595] border border-transparent rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
              >
                Book Appointment
              </a>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
</div>

<style>
  @font-face {
    font-family: 'Ethnocentric';
    src: url('/fonts/Ethnocentric Rg.otf') format('opentype');
  }
  .font-ethnocentric {
    font-family: 'Ethnocentric', sans-serif;
  }
</style>
