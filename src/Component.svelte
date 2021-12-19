<script lang="ts">
  export let clazz: string = '';
  export let items: any[];
  export let itemsLoaded: number = 1;
  export { clazz as class };

  $: displayedItems = items.slice(0, itemsLoaded);

  function inViewport(el: HTMLElement) {
    const rect = el.getBoundingClientRect();
    return (
      rect.top >= 0 &&
      rect.left >= 0 &&
      rect.bottom <=
        (window.innerHeight || document.documentElement.clientHeight) * 2 &&
      rect.right <= (window.innerWidth || document.documentElement.clientWidth)
    );
  }

  async function updateElements(e) {
    const children = e.target.children;
    if (inViewport(children[children.length - 1])) {
      displayedItems = [...displayedItems, ...items.splice(0, itemsLoaded)];
    }
  }
</script>

<style>
  div { overflow-y: scroll; }
</style>

<div
  class={clazz}
  on:scroll={updateElements}
>
  {#each displayedItems as item}
    <slot {item} />
  {/each}
</div>
