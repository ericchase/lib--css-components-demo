<script lang="ts">
  import { browser } from '$app/environment';
  if (browser) {
    window.onmessage = function (e: MessageEvent<{ fontSize: string }>) {
      document.documentElement.style.setProperty('font-size', e.data.fontSize);
    };
  }

  import Demo from '$lib/Demo.svelte';
</script>

<Demo />
