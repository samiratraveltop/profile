<script>
  let { showModal = $bindable(), header, child, closeModal = false } = $props();

  let dialog = $state(); // HTMLDialogElement

  $effect(() => {
    if (showModal) dialog.showModal();
  });
</script>

<!-- svelte-ignore a11y_click_events_have_key_events, a11y_no_noninteractive_element_interactions -->

{#if showModal}
  <dialog
    bind:this={dialog}
    onclose={() => (showModal = false)}
    onclick={(e) => {
      if (e.target === dialog) dialog.close();
    }}
  >
    <div>
      {@render header?.()}
      <!-- <hr /> -->
      {@render child?.()}
      {#if closeModal}
        <hr />
        <!-- svelte-ignore a11y_autofocus -->
        <button autofocus onclick={() => dialog.close()}>close modal</button>
      {/if}
    </div>
  </dialog>
{/if}

<style>
  dialog {
    display: flex;
    max-width: 80%;
    min-width: 30%;
    min-height: 20%;
    border-radius: 0.2em;
    border: none;
    padding: 0;
    align-self: center;
    justify-self: center;
  }
  dialog::backdrop {
    background: rgba(0, 0, 0, 0.3);
  }
  dialog > div {
    padding: 1em;
    width: 100%;
    height: auto;
  }
  dialog[open] {
    animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  }
  @keyframes zoom {
    from {
      transform: scale(0.95);
    }
    to {
      transform: scale(1);
    }
  }
  dialog[open]::backdrop {
    animation: fade 0.2s ease-out;
  }
  @keyframes fade {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  button {
    display: block;
  }

  :global(dialog iframe) {
    width: 100%;
  }

  ::-webkit-scrollbar {
    width: 0px;
    height: 0px;
  }
  ::-webkit-scrollbar-button {
    width: 0px;
    height: 0px;
  }
  ::-webkit-scrollbar-thumb {
    background: transparent;
    border: 0px none;
    border-radius: 0px;
  }
  ::-webkit-scrollbar-thumb:hover {
    background: transparent;
  }
  ::-webkit-scrollbar-thumb:active {
    background: transparent;
  }
  ::-webkit-scrollbar-track {
    background: transparent;
    border: 0px none;
    border-radius: 0px;
  }
  ::-webkit-scrollbar-track:hover {
    background: transparent;
  }
  ::-webkit-scrollbar-track:active {
    background: transparent;
  }
  ::-webkit-scrollbar-corner {
    background: transparent;
  }
</style>
