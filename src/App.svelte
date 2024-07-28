<script lang="ts">
  import { Accordion, AccordionItem } from './lib/components/acoordion';
  import Button from './lib/components/button/button.svelte';

  const items = [
    {title: "item 1", content: "Content 1"},
    {title: "item 2", content: "Content 2"},
    {title: "item 3", content: "Content 3"},
    {title: "item 4", content: "Content 4"},
    {title: "item 5", content: "Content 5"},
  ]
</script>

<main>
  <h1>TEXT</h1>
  <Button variant="primary" disabled={true}>Hola</Button>
  <p data-ui="primary outline size">Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita, voluptatem eveniet illo provident doloribus ab soluta placeat cum assumenda! Magnam explicabo repellendus nostrum corrupti accusantium reprehenderit nobis odit autem eveniet.</p>
  <section>
    <Accordion>
      {#each items as item}
      <AccordionItem>
        <svelte:fragment slot="title">{item.title}</svelte:fragment>
        <small slot="subtitle">Subtitle</small>
        <svelte:fragment slot="content">{item.content}</svelte:fragment>
      </AccordionItem>
      {/each}
    </Accordion>
  </section>
</main>

<style>
  h1 {
    font-family: Jost, sans-serif;
    font-weight: bold;
    font-size: var(--font-size-fluid-3);
    background-image: linear-gradient(indigo, hotpink);
    background-clip: text;
    color: transparent;
  }
</style>
