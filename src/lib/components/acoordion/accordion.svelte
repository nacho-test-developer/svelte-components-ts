<script lang="ts">
  export const collapse = false
</script>

<div class="accordion">
  <slot />
</div>

<style>
  .accordion {
    background-color: var(--accordion-background-color, white);
    border-radius: var(--accordion-background-radius, 0.5rem);
    color: var(--accordion-color, black);
    padding: var(--accordion-padding, 1rem);
    width: var(--accordion-width, 60ch);
  }

  .accordion:has(:global(.accordion-item__title)) {
    opacity: 0.1;
  }
</style>