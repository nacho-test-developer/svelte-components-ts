<script lang="ts">
  import { slide } from 'svelte/transition';
  export let open: boolean = false

  function toggle() {
    open = !open
  }
</script>

<div class="accordion-item">
  <button on:click={toggle} class="accordion-item__toggle">
    <span class="accordion-item__title">
      {#if $$slots.title}
      <h6>
        <slot name="title" />
      </h6>
      {/if}
      <slot name="subtitle" />
    </span>
    <span class="accordion-item__icon">{#if open}🔺{:else}🔻{/if}</span>
  </button>

  {#if open}
  <div transition:slide|local class="accordion-item__content">
    <slot name="content" />
  </div>
  {/if}
</div>

<style>
  h6 {
    color: var(--gray-12);
    font-size: var(--font-size-1);
    margin: 0;
  }
  .accordion-item {
    color: black;
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  .accordion-item__toggle {
    align-items: center;
    background-color: unset;
    border: 0;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    font-size: initial;
    padding: unset;
    text-align: left;
  }
  .accordion-item__toggle:hover {
    background-color: hsla(330, 100%, 71%, 0.07);
  }

  .accordion-item__title :global(> [slot]) {
    color: black;
  }

  .accordion-item__content {
    padding: 2rem 1rem;
  }
</style>