<script lang="ts">
  // Toggle Button Demo
  let isToggled = false;
  function toggle() {
    isToggled = !isToggled;
  }

  // Tabs Demo
  let activeTab = 1;
  function activateTab(id: number) {
    activeTab = id;
  }
  import cat1 from '$lib/images/cat1.jpg';
  import cat2 from '$lib/images/cat2.jpg';
  import cat3 from '$lib/images/cat3.jpg';
</script>

<main class="column">
  <button>Button</button>
  <!-- Toggle Button Demo -->
  <button class="state" class:on={isToggled} on:click={toggle}>Toggle Button</button>
  <!-- Tabs Demo -->
  <div class="tabs">
    <div>
      <button class="state" class:on={activeTab === 1} on:click={() => activateTab(1)}>One</button>
      <button class="state" class:on={activeTab === 2} on:click={() => activateTab(2)}>Two</button>
      <button class="state" class:on={activeTab === 3} on:click={() => activateTab(3)}>Three</button>
    </div>
    <div class="cat-picture">
      {#if activeTab === 1}
        <img src={cat1} alt="" />
      {:else if activeTab === 2}
        <img src={cat2} alt="" />
      {:else if activeTab === 3}
        <img src={cat3} alt="" />
      {/if}
    </div>
  </div>
</main>

<style>
  main {
    font-size: 1rem;
  }

  .column {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1em;
  }

  .tabs {
    border-color: lightgray;
    border-radius: 0.375em;
    border-style: solid;
    border-width: 0.125em;
    padding: 0.125em;
  }
  .tabs > .cat-picture {
    padding-block-start: 0.125em;
    line-height: 0; /* remove spacing underneath image */
  }
  .tabs > .cat-picture > img {
    border-radius: 0.375em;
    inline-size: 100%;
    aspect-ratio: 1/1;
  }
</style>
