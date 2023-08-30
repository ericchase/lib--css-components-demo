<script lang="ts">
  import { browser } from '$app/environment';

  let iframeDefault: HTMLIFrameElement;
  let iframeDemo: HTMLIFrameElement;

  let fontSize = 1;
  $: if (browser) {
    document.documentElement.style.setProperty('font-size', fontSize + 'rem');
    iframeDefault?.contentWindow?.postMessage({ fontSize: `${fontSize}rem` });
    iframeDemo?.contentWindow?.postMessage({ fontSize: `${fontSize}rem` });
  }
</script>

<section>
  <div class="column">
    <label>Change :root font size: <input type="number" bind:value={fontSize} step="0.1" /></label>
    <div class="row">
      <iframe bind:this={iframeDefault} width="100%" height="100%" title="Default" src="/default" />
      <iframe bind:this={iframeDemo} width="100%" height="100%" title="Demo" src="/demo" />
    </div>
  </div>
</section>

<style>
  section {
    block-size: 100%;
    box-sizing: border-box;
  }

  .column {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1em;
    block-size: 100%;
    inline-size: 100%;
    box-sizing: border-box;
  }
  .row {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    gap: 1em;
    block-size: 100%;
    inline-size: 100%;
    box-sizing: border-box;
  }

  label {
    font-size: 16px;
  }
</style>
