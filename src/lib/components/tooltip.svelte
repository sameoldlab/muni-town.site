<script lang="ts">
  let { content, children } = $props();
  const id = Math.random();
  let btn: HTMLButtonElement = $state(null)
  const bcr = $derived(btn?.getBoundingClientRect())

  const position = (e: ToggleEvent) => {
    if (e.newState === "open") {
      console.log(bcr)
      Object.assign(e.target.style, {
        left: (bcr.left +bcr.width / 2 )+ "px",
        top: bcr.top + "px",
      });
    }
  };
</script>

<button
  bind:this={btn}
  popovertarget={id.toString()}
>
  {@render children()}</button
>

<div ontoggle={position} id={id.toString()} popover="auto">
  {@render content()}
</div>

<style>
  button {
    background: none;
    color: inherit;
    border: 0;
    text-decoration: underline;
  }
  div {
    margin: o;
    position: absolute;
    padding: 1rem;
    padding-top: .75rem;
    max-width: 40ch;
    line-height: 125%;
    font-size: 1.4rem;
    border: 1px solid black;
    transform: translate(-50%, 2rem);
    border-radius: 4px;
    background: var(--purple);
    color: black;
  }
</style>
