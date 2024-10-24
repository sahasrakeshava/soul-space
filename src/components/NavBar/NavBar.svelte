<script>
  import { fade, slide } from "svelte/transition"; // Import transitions from Svelte
  let isOpen = false;

  const toggleMenu = () => {
    isOpen = !isOpen;
  };
</script>

<nav class="p-4 bg-purple-800">
  <!-- Dark purple background -->
  <div class="container flex items-center justify-between mx-auto">
    <h1 class="text-2xl font-bold text-white">Brain Chill</h1>
    <button class="text-white md:hidden" on:click={toggleMenu}> ☰ </button>

    <div class="flex space-x-4 md:flex">
      <a href="/" class="text-white hover:underline">Home</a>
      <a href="/resource-hub" class="text-white hover:underline">Resource Hub</a
      >
      <a href="/community-forum" class="text-white hover:underline"
        >Community Forum</a
      >
      <a href="/self-care-tools" class="text-white hover:underline"
        >Self-Care Tools</a
      >
    </div>

    {#if isOpen}
      <!-- Only show the mobile menu if isOpen is true -->
      <div class="md:hidden" transition:fade={{ duration: 200 }}>
        <div
          class="flex flex-col p-4 mt-2 space-y-2 bg-purple-900 rounded-lg shadow-lg"
        >
          <a href="/" class="text-white hover:underline" transition:slide
            >Home</a
          >
          <a
            href="/resource-hub"
            class="text-white hover:underline"
            transition:slide>Resource Hub</a
          >
          <a
            href="/community-forum"
            class="text-white hover:underline"
            transition:slide>Community Forum</a
          >
          <a
            href="/self-care-tools"
            class="text-white hover:underline"
            transition:slide>Self-Care Tools</a
          >
        </div>
      </div>
    {/if}
  </div>
</nav>
