<script>
  import { fade } from 'svelte/transition';

  let formData = {
    name: '',
    email: '',
    phone: '',
    message: ''
  };

  const contactInfo = [
    {
      icon: 'location',
      title: 'Address',
      content: 'Madavoor Road, Pallickal\nTrivandrum Dist - 695604'
    },
    {
      icon: 'phone',
      title: 'Phone',
      content: '+91 8943893499 / 894383491'
    },
    {
      icon: 'email',
      title: 'Email',
      content: 'info@valsalyaclinic.com'
    }
  ];

  function handleSubmit() {
    // Handle form submission
    console.log('Form submitted:', formData);
    // Reset form
    formData = {
      name: '',
      email: '',
      phone: '',
      message: ''
    };
  }
</script>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#5CA595]/10 to-white">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold text-black mb-6">Contact Us</h1>
        <p class="text-xl text-black">
          Get in touch with us for any questions or to schedule an appointment
        </p>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section class="py-20">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
        <!-- Contact Form -->
        <div class="bg-white rounded-lg shadow-lg p-8" in:fade={{ duration: 500 }}>
          <h2 class="text-2xl font-bold text-black mb-6">Send us a Message</h2>
          <form on:submit|preventDefault={handleSubmit} class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-medium text-black mb-1">Name</label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#5CA595] focus:border-[#5CA595]"
                required
              />
            </div>
            <div>
              <label for="phone" class="block text-sm font-medium text-black mb-1">Phone</label>
              <input
                type="tel"
                id="phone"
                bind:value={formData.phone}
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#5CA595] focus:border-[#5CA595]"
                required
              />
            </div>
            <div>
              <label for="email" class="block text-sm font-medium text-black mb-1">Email</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#5CA595] focus:border-[#5CA595]"
                required
              />
            </div>
            <div>
              <label for="message" class="block text-sm font-medium text-black mb-1">Message</label>
              <textarea
                id="message"
                bind:value={formData.message}
                rows="4"
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#5CA595] focus:border-[#5CA595]"
                required
              ></textarea>
            </div>
            <button
              type="submit"
              class="w-full bg-[#5CA595] text-white px-6 py-3 rounded-md hover:bg-[#5CA595]/90 transition-colors duration-200"
            >
              Send Message
            </button>
          </form>
        </div>

        <!-- Contact Info -->
        <div class="space-y-8" in:fade={{ duration: 500, delay: 200 }}>
          <div class="bg-white rounded-lg shadow-lg p-8">
            <h2 class="text-2xl font-bold text-black mb-6">Contact Information</h2>
            <div class="space-y-6">
              {#each contactInfo as info}
                <div class="flex items-start space-x-4">
                  <span class="text-[#5CA595] mt-1">
                    {#if info.icon === 'location'}
                      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                      </svg>
                    {:else if info.icon === 'phone'}
                      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                      </svg>
                    {:else if info.icon === 'email'}
                      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                      </svg>
                    {/if}
                  </span>
                  <div>
                    <h3 class="text-lg font-semibold text-black">{info.title}</h3>
                    <p class="text-black">{info.content}</p>
                  </div>
                </div>
              {/each}
            </div>
          </div>

          <!-- Map -->
          <div class="bg-white rounded-lg shadow-lg overflow-hidden">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3945.123456789012!2d76.81084550320745!3d8.824843401289542!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zOMKwNDknMjkuNCJOIDc2wrA0OCczOS4wIkU!5e0!3m2!1sen!2sin!4v1234567890"
              width="100%"
              height="300"
              style="border:0;"
              allowfullscreen={true}
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </section>
</div> 