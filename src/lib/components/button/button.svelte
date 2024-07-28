<!-- <svelte:options customElement={{ tag: 'my-button' }} /> -->

<script lang="ts">
  export const variant:string = 'primary'
  export const disabled:boolean = false
</script>

<button class="button {variant}" {disabled} on:click={() => console.log('click')}>
  <slot />
</button>

<style>
  .primary {
    color: var(--teal-12);
  }
</style>