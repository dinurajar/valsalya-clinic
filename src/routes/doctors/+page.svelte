<script>
  import { fade } from 'svelte/transition';

  const doctors = [
    {
      name: 'Dr. Sarah Johnson',
      specialization: 'Internal Medicine',
      image: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '20+ years',
      description: 'Dr. Johnson is a board-certified internal medicine specialist with extensive experience in managing complex medical conditions.',
      education: ['MD - Harvard Medical School', 'Residency - Massachusetts General Hospital'],
      languages: ['English', 'Spanish']
    },
    {
      name: 'Dr. Michael Chen',
      specialization: 'Cardiology',
      image: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '15+ years',
      description: 'Dr. Chen specializes in advanced cardiac care and has been instrumental in developing our cardiac care program.',
      education: ['MD - Stanford University', 'Fellowship - Cleveland Clinic'],
      languages: ['English', 'Mandarin']
    },
    {
      name: 'Dr. Emily Rodriguez',
      specialization: 'Pediatrics',
      image: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '12+ years',
      description: 'Dr. Rodriguez brings warmth and expertise to our pediatric department, ensuring the best care for our youngest patients.',
      education: ['MD - Johns Hopkins University', 'Residency - Children\'s Hospital of Philadelphia'],
      languages: ['English', 'Spanish', 'French']
    },
    {
      name: 'Dr. James Wilson',
      specialization: 'Orthopedics',
      image: 'https://images.unsplash.com/photo-1612349317150-e413f6a5b16d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80',
      experience: '18+ years',
      description: 'Dr. Wilson is a renowned orthopedic surgeon specializing in joint replacement and sports medicine.',
      education: ['MD - Yale University', 'Fellowship - Mayo Clinic'],
      languages: ['English', 'German']
    }
  ];
</script>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#3F7D20]/10 to-white">
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
                  class="w-full h-full object-cover"
                />
              </div>
              <div class="p-6 md:w-2/3">
                <h3 class="text-xl font-bold text-gray-900 mb-2">{doctor.name}</h3>
                <p class="text-[#3F7D20] font-medium mb-4">{doctor.specialization}</p>
                <p class="text-gray-600 mb-4">{doctor.description}</p>
                <div class="space-y-2">
                  <p class="text-sm text-gray-600">
                    <span class="font-medium">Experience:</span> {doctor.experience}
                  </p>
                  <div class="text-sm text-gray-600">
                    <span class="font-medium">Education:</span>
                    <ul class="list-disc list-inside mt-1">
                      {#each doctor.education as edu}
                        <li>{edu}</li>
                      {/each}
                    </ul>
                  </div>
                  <div class="text-sm text-gray-600">
                    <span class="font-medium">Languages:</span> {doctor.languages.join(', ')}
                  </div>
                </div>
                <div class="mt-6">
                  <a
                    href="/appointment"
                    class="inline-flex items-center justify-center px-6 py-2 text-sm font-medium text-white bg-[#3F7D20] border border-transparent rounded-md hover:bg-[#3F7D20]/90 transition-colors duration-200"
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

  <!-- CTA Section -->
  <section class="py-20 bg-[#3F7D20]/5">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Looking for a Specific Specialist?</h2>
        <p class="text-lg text-gray-600 mb-8">
          Contact us to find the right doctor for your needs or to schedule a consultation.
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a
            href="/appointment"
            class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-white bg-[#3F7D20] border border-transparent rounded-md hover:bg-[#3F7D20]/90 transition-colors duration-200"
          >
            Book Appointment
          </a>
        </div>
      </div>
    </div>
  </section>
</div> 