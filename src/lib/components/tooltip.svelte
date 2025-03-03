<script lang="ts">
  let { content, children } = $props();
  const id = Math.random();
  let btn: HTMLButtonElement = $state(null)

  const position = (e: ToggleEvent) => {
    if (e.newState === "open") {
      const bcr = btn?.getBoundingClientRect()
      Object.assign(e.target.style, {
        left: (bcr.left +bcr.width / 2 )+ "px",
        top: (bcr.top + window.scrollY) + "px",
        opacity: 1
      });
    } else {
      Object.assign(e.target.style, {
        opacity: 0
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
    opacity: 0;
    margin: 0;
    transition: opacity 160ms ease-in;;
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
