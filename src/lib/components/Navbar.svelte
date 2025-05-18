<script>
  import { page } from '$app/stores';
  import { onMount } from 'svelte';
  
  const navItems = [
    { href: '/', label: 'Home' },
    { href: '/services', label: 'Services' },
    { href: '/doctors', label: 'Doctors' },
    { href: '/laboratory', label: 'Laboratory' },
    { href: '/pharmacy', label: 'Pharmacy' },
    { href: '/contact', label: 'Contact' }
  ];

  let isMenuOpen = false;

  onMount(() => {
    // Initialize any necessary state
  });
</script>

<nav class="bg-[#5CA595] shadow-lg fixed w-full z-50">
  <div class="container mx-auto px-4">
    <div class="flex justify-between items-center h-20">
      <!-- Logo -->
      <a href="/" class="flex items-center space-x-2">
        <img src="/images/Valsalya.png" alt="Valsalya Logo" class="h-16 w-auto" />
      </a>

      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center space-x-8">
        {#each navItems as item}
          <a
            href={item.href}
            class="text-white hover:text-[#f0f9f8] transition-colors duration-200 text-lg font-bold {$page.url.pathname === item.href ? 'text-[#f0f9f8]' : ''}"
          >
            {item.label === 'Contact' ? 'Contact Us' : item.label}
          </a>
        {/each}
        <a
          href="/appointment"
          class="bg-white text-[#5CA595] px-6 py-2 rounded-md hover:bg-[#f0f9f8] hover:text-[#5CA595] transition-colors duration-200 text-lg font-bold"
        >
          Book Appointment
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <div class="md:hidden flex items-center space-x-4">
        <button
          class="text-white hover:text-[#f0f9f8]"
          on:click={() => (isMenuOpen = !isMenuOpen)}
        >
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Navigation -->
    {#if isMenuOpen}
      <div class="md:hidden py-4 bg-[#5CA595]">
        {#each navItems as item}
          <a
            href={item.href}
            class="block py-2 text-white hover:text-[#f0f9f8] transition-colors duration-200 text-lg font-bold {$page.url.pathname === item.href ? 'text-[#f0f9f8]' : ''}"
          >
            {item.label === 'Contact' ? 'Contact Us' : item.label}
          </a>
        {/each}
        <a
          href="/appointment"
          class="block mt-4 bg-white text-[#5CA595] px-6 py-2 rounded-md hover:bg-[#f0f9f8] hover:text-[#5CA595] transition-colors duration-200 text-center text-lg font-bold"
        >
          Book Appointment
        </a>
      </div>
    {/if}
  </div>
</nav>

<style>
  @font-face {
    font-family: 'Ethnocentric';
    src: url('/fonts/Ethnocentric Rg.otf') format('opentype');
  }
  .font-ethnocentric {
    font-family: 'Ethnocentric', sans-serif;
  }
</style> 