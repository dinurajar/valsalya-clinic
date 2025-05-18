<script>
  import { fade } from 'svelte/transition';

  let formData = {
    name: '',
    email: '',
    phone: '',
    date: '',
    time: '',
    department: '',
    doctor: '',
    message: ''
  };

  const departments = [
    'General Medicine',
    'Cardiology',
    'Orthopedics',
    'Pediatrics',
    'Gynecology',
    'Dermatology'
  ];

  const timeSlots = [
    '09:00 AM',
    '10:00 AM',
    '11:00 AM',
    '02:00 PM',
    '03:00 PM',
    '04:00 PM'
  ];

  function handleSubmit() {
    // Handle form submission
    console.log('Form submitted:', formData);
    // Reset form
    formData = {
      name: '',
      email: '',
      phone: '',
      date: '',
      time: '',
      department: '',
      doctor: '',
      message: ''
    };
  }
</script>

<div class="bg-white">
  <!-- Hero Section -->
  <section class="relative py-20 bg-gradient-to-r from-[#3F7D20]/10 to-white">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Book an Appointment</h1>
        <p class="text-xl text-gray-600">
          Schedule your visit with our expert medical professionals
        </p>
      </div>
    </div>
  </section>

  <!-- Appointment Form Section -->
  <section class="py-20">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto">
        <div class="bg-white rounded-lg shadow-lg p-8" in:fade={{ duration: 500 }}>
          <form on:submit|preventDefault={handleSubmit} class="space-y-6">
            <!-- Personal Information -->
            <div class="space-y-6">
              <h2 class="text-2xl font-bold text-gray-900">Personal Information</h2>
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
                  <input
                    type="text"
                    id="name"
                    bind:value={formData.name}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  />
                </div>
                <div>
                  <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                  <input
                    type="email"
                    id="email"
                    bind:value={formData.email}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  />
                </div>
                <div>
                  <label for="phone" class="block text-sm font-medium text-gray-700 mb-1">Phone Number</label>
                  <input
                    type="tel"
                    id="phone"
                    bind:value={formData.phone}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  />
                </div>
              </div>
            </div>

            <!-- Appointment Details -->
            <div class="space-y-6">
              <h2 class="text-2xl font-bold text-gray-900">Appointment Details</h2>
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="department" class="block text-sm font-medium text-gray-700 mb-1">Department</label>
                  <select
                    id="department"
                    bind:value={formData.department}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  >
                    <option value="">Select Department</option>
                    {#each departments as dept}
                      <option value={dept}>{dept}</option>
                    {/each}
                  </select>
                </div>
                <div>
                  <label for="doctor" class="block text-sm font-medium text-gray-700 mb-1">Preferred Doctor (Optional)</label>
                  <input
                    type="text"
                    id="doctor"
                    bind:value={formData.doctor}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                  />
                </div>
                <div>
                  <label for="date" class="block text-sm font-medium text-gray-700 mb-1">Preferred Date</label>
                  <input
                    type="date"
                    id="date"
                    bind:value={formData.date}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  />
                </div>
                <div>
                  <label for="time" class="block text-sm font-medium text-gray-700 mb-1">Preferred Time</label>
                  <select
                    id="time"
                    bind:value={formData.time}
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                    required
                  >
                    <option value="">Select Time</option>
                    {#each timeSlots as slot}
                      <option value={slot}>{slot}</option>
                    {/each}
                  </select>
                </div>
              </div>
            </div>

            <!-- Additional Information -->
            <div class="space-y-6">
              <h2 class="text-2xl font-bold text-gray-900">Additional Information</h2>
              <div>
                <label for="message" class="block text-sm font-medium text-gray-700 mb-1">Message (Optional)</label>
                <textarea
                  id="message"
                  bind:value={formData.message}
                  rows="4"
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-[#3F7D20] focus:border-[#3F7D20]"
                  placeholder="Please provide any additional information that might help us better assist you."
                ></textarea>
              </div>
            </div>

            <button
              type="submit"
              class="w-full bg-[#3F7D20] text-white px-6 py-3 rounded-md hover:bg-[#3F7D20]/90 transition-colors duration-200"
            >
              Book Appointment
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>

  <!-- Additional Information Section -->
  <section class="py-20 bg-[#3F7D20]/5">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center" in:fade={{ duration: 500 }}>
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Need Help?</h2>
        <p class="text-lg text-gray-600 mb-8">
          If you have any questions or need assistance with booking your appointment, our team is here to help.
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a
            href="/contact"
            class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-[#3F7D20] bg-white border border-[#3F7D20] rounded-md hover:bg-[#3F7D20]/10 transition-colors duration-200"
          >
            Contact Us
          </a>
          <a
            href="tel:+15551234567"
            class="inline-flex items-center justify-center px-8 py-3 text-base font-medium text-white bg-[#3F7D20] border border-transparent rounded-md hover:bg-[#3F7D20]/90 transition-colors duration-200"
          >
            Call Us
          </a>
        </div>
      </div>
    </div>
  </section>
</div> 