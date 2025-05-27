<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  const pharmacyServices = [
    {
      title: 'Prescription Medications',
      description: 'Full range of prescription medications with expert guidance from our pharmacists.',
      icon: 'M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z'
    },
    {
      title: 'Over-the-Counter Products',
      description: 'Wide selection of OTC medications, health supplements, and personal care items.',
      icon: 'M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z'
    },
    {
      title: 'Medication Counseling',
      description: 'Personalized medication counseling and guidance from our experienced pharmacists.',
      icon: 'M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z'
    },
    {
      title: 'Home Delivery',
      description: 'Convenient medication delivery service for patients who cannot visit the pharmacy.',
      icon: 'M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z'
    },
    {
      title: 'Health Monitoring',
      description: 'Blood pressure, blood sugar, and other health parameter monitoring services.',
      icon: 'M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z'
    },
    {
      title: 'Specialty Medications',
      description: 'Access to specialty medications and rare disease treatments with expert support.',
      icon: 'M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z'
    }
  ];

  const features = [
    {
      title: 'Expert Pharmacists',
      description: 'Our team of qualified pharmacists provides expert guidance and medication counseling.'
    },
    {
      title: 'Wide Selection',
      description: 'Comprehensive range of medications and healthcare products available.'
    },
    {
      title: 'Quick Service',
      description: 'Efficient prescription filling and medication dispensing services.'
    },
    {
      title: 'Medication Management',
      description: 'Help with medication schedules, interactions, and proper usage instructions.'
    }
  ];

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<svelte:head>
  <title>Pharmacy Services - Valsalya Speciality Clinic</title>
  <meta name="description" content="Comprehensive pharmacy services including prescription medications, OTC products, and medication counseling at Valsalya Speciality Clinic." />
</svelte:head>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#5CA595]/10 to-white">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Pharmacy Services</h1>
        <p class="text-xl text-gray-600">
          Comprehensive medication services with expert guidance
        </p>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="py-16 bg-white">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each pharmacyServices as service}
          <div class="bg-white rounded-lg shadow-lg p-6 hover:shadow-xl transition-shadow" in:fade={{ duration: 500, delay: 200 }}>
            <div class="text-[#5CA595] mb-4">
              <svg class="w-12 h-12" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d={service.icon} />
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-2">{service.title}</h3>
            <p class="text-gray-600">{service.description}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Features Section -->
  <section class="py-16 bg-[#5CA595]/10">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12 text-[#5CA595]">Why Choose Our Pharmacy?</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        {#each features as feature}
          <div class="bg-white rounded-lg p-6 shadow-md" in:fade={{ duration: 500, delay: 300 }}>
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