<script>
  import { fade, slide } from "svelte/transition"; // Import transitions from Svelte
  let isOpen = false;

  const toggleMenu = () => {
    isOpen = !isOpen;
  };
</script>

<nav class="bg-purple-800 p-4">
  <!-- Dark purple background -->
  <div class="container mx-auto flex justify-between items-center">
    <h1 class="text-white text-2xl font-bold">SoulSpace</h1>
    <button class="md:hidden text-white" on:click={toggleMenu}> ☰ </button>

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
          class="flex flex-col space-y-2 mt-2 bg-purple-900 p-4 rounded-lg shadow-lg"
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
