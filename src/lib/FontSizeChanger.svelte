<script lang="ts">
  // Allow user to change :root font-size property.
  import { browser } from '$app/environment';
  let fontSize = 1;
  $: if (browser) {
    document.documentElement.style.setProperty('font-size', fontSize + 'rem');
  }
</script>

<label>Change :root font size: <input type="number" bind:value={fontSize} step="0.1" /></label>
<br />
<br />
<br />
<br />

<style>
  label {
    font-size: 16px;
  }
</style>
