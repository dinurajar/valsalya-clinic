<script>
  import { fade } from 'svelte/transition';

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
    },
    {
      name: 'Dr. Mohammed Shameer',
      specialization: 'MBBS, MS ENT',
      role: 'Consultant ENT Surgeon',
      timing: 'Wednesday & Saturday 7 PM to 8:30 PM',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Devi Gayathri',
      specialization: 'MBBS, DNB',
      role: 'Consultant Gynaecologist',
      timing: 'Tuesday 1:30 PM to 3:30 PM',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Muhammed Rameez',
      specialization: 'BPT',
      role: 'Consultant Physiotherapist',
      timing: 'Monday, Wednesday & Friday 10 AM to 1 PM',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Nafeer Sha H',
      specialization: 'MBBS',
      role: 'General Practitioner',
      timing: '',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Vivek S',
      specialization: 'MBBS',
      role: 'General Practitioner',
      timing: '',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Nabeel Muhammed',
      specialization: 'MBBS',
      role: 'General Practitioner',
      timing: '',
      image: '/images/placeholder.png'
    },
    {
      name: 'Dr. Jameen Najeeb',
      specialization: 'MBBS',
      role: 'General Practitioner',
      timing: '',
      image: '/images/placeholder.png'
    }
  ];
</script>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#5CA595]/10 to-white">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Our Doctors</h1>
        <p class="text-xl text-gray-600">
          Meet our team of experienced and dedicated medical professionals
        </p>
      </div>
    </div>
  </section>

  <!-- Doctors Grid -->
  <section class="py-20">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
        {#each doctors as doctor, i}
          <div
            class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow duration-300"
            in:fade={{ duration: 500, delay: i * 100 }}
          >
            <div class="md:flex">
              <div class="md:w-1/3">
                <img
                  src={doctor.image}
                  alt={doctor.name}
                  class="w-full h-full object-contain"
                />
              </div>
              <div class="p-6 md:w-2/3">
                <h3 class="text-xl font-bold text-gray-900 mb-2">{doctor.name}</h3>
                <p class="text-[#5CA595] font-medium mb-2">{doctor.specialization}</p>
                <p class="text-gray-600 mb-2">{doctor.role}</p>
                {#if doctor.timing}
                  <p class="text-sm text-gray-600">
                    <span class="font-medium">Timing:</span> {doctor.timing}
                  </p>
                {/if}
                <div class="mt-6">
                  <a
                    href="/appointment"
                    class="inline-flex items-center justify-center px-6 py-2 text-sm font-medium text-white bg-[#5CA595] border border-transparent rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
                  >
                    Book Appointment
                  </a>
                </div>
              </div>
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