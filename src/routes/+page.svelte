<script lang="ts">
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  import Hero from '$lib/components/Hero.svelte';

  let currentSlide = 0;
  const slides = [
    {
      title: "Welcome to Valsalya Speciality Clinic",
      description: "Your trusted healthcare partner providing comprehensive medical services with compassion and excellence.",
      image: "https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
      cta: "Book an Appointment",
      ctaLink: "/appointment"
    },
    {
      title: "24 Hours Casualty",
      description: "<span class='text-3xl md:text-4xl font-bold block mb-2'>WHEN EVERY SECOND COUNTS...</span> Fully equipped emergency room <span class='font-bold text-red-500'>OPEN 24/7</span> with the fastest response in the region.",
      image: "https://images.unsplash.com/photo-1587351021759-3e566b6af7cc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
      cta: "Emergency Contact",
      ctaLink: "/contact"
    },
    {
      title: "24 Hours Laboratory",
      description: "<span class='text-3xl md:text-4xl font-bold block mb-2'>24 Hours Laboratory</span> Advanced diagnostic services available 24/7. Quick and accurate test results with modern equipment and expert technicians.",
      image: "https://images.unsplash.com/photo-1559757175-5700dde67548?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80",
      cta: "View Services",
      ctaLink: "/laboratory"
    },
    {
      title: "24 Hours Pharmacy",
      description: "Full-service pharmacy open 24/7. Wide range of medications, expert consultation, and quick service for all your pharmaceutical needs.",
      image: "https://images.unsplash.com/photo-1584308666744-24d5c474f2ae?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
      cta: "Learn More",
      ctaLink: "/pharmacy"
    }
  ];

  let autoplayInterval: ReturnType<typeof setInterval> | undefined;

  onMount(() => {
    startAutoplay();
    return () => {
      if (autoplayInterval) clearInterval(autoplayInterval);
    };
  });

  function startAutoplay() {
    autoplayInterval = setInterval(() => {
      currentSlide = (currentSlide + 1) % slides.length;
    }, 5000);
  }

  function goToSlide(index: number) {
    currentSlide = index;
    if (autoplayInterval) clearInterval(autoplayInterval);
    startAutoplay();
  }

  const featuredServices = [
    {
      title: 'General Medicine',
      description: 'Comprehensive primary healthcare services for adults, including preventive care, diagnosis, and treatment of various medical conditions. Our experienced physicians provide personalized care for your overall health and well-being.',
      icon: 'M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z',
      image: 'https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80'
    },
    {
      title: 'Orthopaedics',
      description: 'Expert care for bone and joint disorders, sports injuries, and musculoskeletal conditions. Our orthopedic specialists use advanced techniques and technology to help you regain mobility and live pain-free.',
      icon: 'M7 12l3-3 3 3 4-4M8 21l4-4 4 4M3 4h18M4 4h16v12a1 1 0 01-1 1H5a1 1 0 01-1-1V4z',
      image: 'https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80'
    },
    {
      title: 'General Surgery',
      description: 'Comprehensive surgical care for various conditions, including minimally invasive procedures and advanced surgical techniques. Our skilled surgeons are committed to providing safe and effective surgical solutions.',
      icon: 'M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2',
      image: 'https://images.unsplash.com/photo-1587351021759-3e566b6af7cc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80'
    }
  ];

  const featuredDoctors = [
    {
      name: 'Dr. Sarah Johnson',
      specialization: 'Internal Medicine',
      image: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '20+ years',
      description: 'Dr. Johnson is a board-certified internal medicine specialist with extensive experience in managing complex medical conditions.'
    },
    {
      name: 'Dr. Michael Chen',
      specialization: 'Cardiology',
      image: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '15+ years',
      description: 'Dr. Chen specializes in advanced cardiac care and has been instrumental in developing our cardiac care program.'
    }
  ];
</script>

<!-- Hero Section with Carousel -->
<section class="relative h-[600px] overflow-hidden">
  {#each slides as slide, i}
    <div
      class="absolute inset-0 transition-opacity duration-1000"
      style="opacity: {currentSlide === i ? 1 : 0}; z-index: {currentSlide === i ? 1 : 0}"
    >
      <div class="absolute inset-0 bg-black/40 z-10"></div>
      <img
        src={slide.image}
        alt={slide.title}
        class="w-full h-full object-cover"
      />
      <div class="absolute inset-0 z-20 flex items-center">
        <div class="container mx-auto px-4">
          <div class="max-w-2xl text-white" in:fly={{ y: 20, duration: 500 }}>
            <h1 class="text-4xl md:text-5xl font-bold mb-4">{slide.title}</h1>
            <p class="text-lg md:text-xl mb-8" class:text-lg={slide.title !== "24 Hours Casualty"} class:text-xl={slide.title !== "24 Hours Casualty"}>
              {@html slide.description}
            </p>
            <a
              href={slide.ctaLink}
              class="inline-block bg-[#5CA595] text-white px-8 py-3 rounded-full font-semibold hover:bg-[#5CA595]/90 transition-colors"
            >
              {slide.cta}
            </a>
          </div>
        </div>
      </div>
    </div>
  {/each}

  <!-- Carousel Navigation -->
  <div class="absolute bottom-8 left-0 right-0 z-30 flex justify-center space-x-2">
    {#each slides as _, i}
      <button
        class="w-3 h-3 rounded-full transition-colors {currentSlide === i ? 'bg-[#5CA595]' : 'bg-white/50'}"
        on:click={() => goToSlide(i)}
        aria-label="Go to slide {i + 1}"
      ></button>
    {/each}
  </div>
</section>

<div class="bg-white">
  <!-- Featured Services Section -->
  <section class="py-20 bg-[#5CA595]/5">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-gray-900 mb-4">Our Services</h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Comprehensive healthcare services delivered with expertise and compassion
        </p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        {#each featuredServices as service, i}
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
              <div class="absolute bottom-4 left-4">
                <svg
                  class="w-8 h-8 text-white"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d={service.icon}
                  />
                </svg>
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold text-gray-900 mb-2">{service.title}</h3>
              <p class="text-gray-600">{service.description}</p>
            </div>
          </div>
        {/each}
      </div>
      <div class="text-center mt-12">
        <a
          href="/services"
          class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-white bg-[#5CA595] border border-transparent rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
        >
          View All Services
        </a>
      </div>
    </div>
  </section>

  <!-- Featured Doctors Section -->
  <section class="py-20 bg-[#5CA595]/10">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-gray-900 mb-4">Our Doctors</h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Meet our team of experienced and dedicated medical professionals
        </p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        {#each featuredDoctors as doctor, i}
          <div
            class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow duration-300"
            in:fade={{ duration: 500, delay: i * 100 }}
          >
            <div class="md:flex">
              <div class="md:w-1/3">
                <img
                  src={doctor.image}
                  alt={doctor.name}
                  class="w-full h-full object-cover"
                />
              </div>
              <div class="p-6 md:w-2/3">
                <h3 class="text-xl font-bold text-gray-900 mb-2">{doctor.name}</h3>
                <p class="text-[#5CA595] font-medium mb-4">{doctor.specialization}</p>
                <p class="text-gray-600 mb-4">{doctor.description}</p>
                <p class="text-sm text-gray-600 mb-4">
                  <span class="font-medium">Experience:</span> {doctor.experience}
                </p>
              </div>
            </div>
          </div>
        {/each}
      </div>
      <div class="text-center mt-12">
        <a
          href="/doctors"
          class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-white bg-[#5CA595] border border-transparent rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
        >
          View All Doctors
        </a>
      </div>
    </div>
  </section>

  <!-- CTA Section -->
  <section class="py-20 bg-[#5CA595]/15">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Ready to Experience Quality Healthcare?</h2>
        <p class="text-lg text-gray-600 mb-8">
          Book an appointment with our expert medical professionals and take the first step towards better health.
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a
            href="/appointment"
            class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-white bg-[#5CA595] border border-transparent rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
          >
            Book Appointment
          </a>
          <a
            href="/contact"
            class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-[#5CA595] bg-white border border-[#5CA595] rounded-md hover:bg-[#5CA595]/10 transition-colors duration-200"
          >
            Contact Us
          </a>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- Additional sections will be added here -->

<style>
  @font-face {
    font-family: 'Ethnocentric';
    src: url('/fonts/Ethnocentric Rg.otf') format('opentype');
  }
  .font-ethnocentric {
    font-family: 'Ethnocentric', sans-serif;
  }
</style>
