<script lang="ts">
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  const services = [
    {
      title: "General Medicine",
      description: "Comprehensive primary healthcare services for adults, including preventive care, diagnosis, and treatment of various medical conditions.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"></path></svg>`
    },
    {
      title: "Orthopaedics",
      description: "Specialized care for bone and joint disorders, sports injuries, and musculoskeletal conditions with advanced treatment options.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 12l3-3 3 3 4-4M8 21l4-4 4 4M3 4h18M4 4h16v12a1 1 0 01-1 1H5a1 1 0 01-1-1V4z"></path></svg>`
    },
    {
      title: "General Surgery",
      description: "Expert surgical care for various conditions, including minimally invasive procedures and advanced surgical techniques.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"></path></svg>`
    },
    {
      title: "Dermatology",
      description: "Comprehensive skin care services for various skin conditions, cosmetic procedures, and preventive skin health.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01"></path></svg>`
    },
    {
      title: "Gynaecology",
      description: "Specialized women's health care, including reproductive health, pregnancy care, and treatment of gynecological conditions.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"></path></svg>`
    },
    {
      title: "E.N.T",
      description: "Expert care for ear, nose, and throat conditions, including hearing disorders, sinus problems, and throat conditions.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15.536a5 5 0 001.414 1.414m2.828-9.9a9 9 0 012.728-2.728"></path></svg>`
    },
    {
      title: "Paediatrics",
      description: "Comprehensive healthcare for children from birth through adolescence, focusing on growth, development, and preventive care.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"></path></svg>`
    },
    {
      title: "Physiotherapy",
      description: "Rehabilitation and physical therapy services for injury recovery, pain management, and improved mobility.",
      icon: `<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>`
    }
  ];

  const features = [
    {
      title: "Expert Doctors",
      description: "Highly qualified and experienced medical professionals dedicated to providing the best care."
    },
    {
      title: "Modern Facilities",
      description: "State-of-the-art medical equipment and technology for accurate diagnosis and treatment."
    },
    {
      title: "Comprehensive Care",
      description: "Complete healthcare solutions under one roof for your convenience."
    },
    {
      title: "Patient-Centered",
      description: "Personalized care and attention for every patient's unique needs."
    }
  ];

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<svelte:head>
  <title>Our Services - Valsalya Speciality Clinic</title>
  <meta name="description" content="Comprehensive medical services including general medicine, cardiology, orthopedics, pediatrics, gynecology, and dermatology at Valsalya Speciality Clinic." />
</svelte:head>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#5CA595]/10 to-white">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Our Services</h1>
        <p class="text-lg text-gray-600">
          Comprehensive healthcare services delivered with expertise and compassion
        </p>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="py-16 bg-gray-50">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        {#each services as service}
          <div
            class="bg-white p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow"
            in:fade
          >
            <div class="text-[#5CA595] mb-4" in:fade={{ delay: 200 }}>
              {@html service.icon}
            </div>
            <h3 class="text-xl font-semibold mb-2">{service.title}</h3>
            <p class="text-gray-600">{service.description}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Features Section -->
  <section class="py-16">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12 text-[#5CA595]">Why Choose Us?</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        {#each features as feature}
          <div
            class="text-center p-6 rounded-lg hover:shadow-md transition-shadow"
            in:fade
          >
            <h3 class="text-xl font-semibold mb-3 text-[#5CA595]">{feature.title}</h3>
            <p class="text-gray-600">{feature.description}</p>
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