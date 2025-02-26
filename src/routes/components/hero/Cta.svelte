<script lang="ts">
  // import { enhance } from "$app/forms";
  let isExtra = $state(false);
  let username = $state("");
  const togglePlan = (e: MouseEvent) => {
    e.preventDefault();
    if ((e.currentTarget as HTMLButtonElement).innerText.includes("Extra"))
      isExtra = true;
    else isExtra = false;
  };
</script>

<div class="cta">
  <form>
    <div class="cta-plans">
      <button onclick={togglePlan} role="option" aria-selected={isExtra}
        >Extra weird $25 <span>50% off</span></button
      >
      <button onclick={togglePlan} role="option" aria-selected={!isExtra}
        >Regular Weird <span>free</span></button
      >
    </div>

    <div class="cta-register">
      <label for="username">
        <input
          id="username"
          bind:value={username}
          type="text"
          required
          placeholder="a [name].weird.one"
        />
      </label>
      <button>
        Register
        <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8.14645 3.14645C8.34171 2.95118 8.65829 2.95118 8.85355 3.14645L12.8536 7.14645C13.0488 7.34171 13.0488 7.65829 12.8536 7.85355L8.85355 11.8536C8.65829 12.0488 8.34171 12.0488 8.14645 11.8536C7.95118 11.6583 7.95118 11.3417 8.14645 11.1464L11.2929 8H2.5C2.22386 8 2 7.77614 2 7.5C2 7.22386 2.22386 7 2.5 7H11.2929L8.14645 3.85355C7.95118 3.65829 7.95118 3.34171 8.14645 3.14645Z" fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path></svg>
      </button>
    </div>
  </form>

  <div class="explainers">
    <a href="a">custom domains</a><a href="b">Why the numbers?</a>
  </div>
</div>

<style>
  button {
    border: 0;
    min-width: max-content;
    padding: 0.75rem 2rem;
    min-width: max-content;
    cursor: pointer;
  }
  button,
  input {
    background: oklch(from var(--purple) 0.2 c h / 0.7);
    color: white;
    backdrop-filter: blur(8px);
    font-family: 'Space Mono', monospace;
  }

  form {
    display: grid;
    gap: 0.5rem;
  }
  .cta-plans {
    display: flex;
    border: 1px solid white;
    border-radius: 2px;
    align-items: center;

    button {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      padding-inline-end: 1.5rem;
      gap: 2rem;
      transition: background-color 80ms ease-in-out;
      span {
        padding: 0.5rem 2rem;
        border: 1px solid transparent;
        border-radius: 400px;
        width: fit-content;
      }
      &:hover {
        background: oklch(
          from var(--purple) calc(l - 0.24) calc(c + 0.02) h / 0.8
        );
      }
      &[aria-selected="true"] {
        background: oklch(from var(--purple) calc(l - 0.16) calc(c + 0.02) h);
        span {
          border-color: white;
        }
      }
    }
  }
  .cta-register {
    display: flex;
    border-radius: 2px;
    gap: 0;
    background: #fff4;
    border: 1px solid white;
    label {
      flex: 1 1 0;
      border-radius: 0;
    }
    input {
      width: 100%;
      padding: 1.25rem 3rem;
      border: 0;
    }
    button {
      padding-inline-start: 2rem;
      padding-inline-end: 1.5rem;
      background: oklch(from var(--purple) calc(l - 0.16) calc(c + 0.02) h);
      border-left: 1px solid white;
      display: flex;
      align-items: center;
      gap: 1rem;
      justify-content: space-between;
      svg {
        transition: transform 100ms ease-in;
      }
    &:hover {
      svg {
        transform: translate(4px, 0px);
      }
    }
    }
  }

  .explainers {
    display: flex;
    justify-content: center;
    gap: 8rem;
    padding: 1rem;
    a {
      font-size: 1.4rem;
      color: white;
    }
  }
</style>
