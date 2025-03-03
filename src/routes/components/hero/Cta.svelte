<script lang="ts">
  import Tooltip from "$lib/components/tooltip.svelte";
  let plan = $state("regular");
  let username = $state("");
</script>

<div class="cta">
  <form
    onsubmit={(e: SubmitEvent) => {
      e.preventDefault();
      // reroute to weird.one/route/to/register?username=${username}&plan={plan}
    }}
  >
    <fieldset class="plans_toggle">
      <legend>Select a Plan</legend>
      <div class="plans_toggle-content">
        <input
          type="radio"
          name="plan"
          value="extra"
          id="plan-extra"
          bind:group={plan}
        />
        <label for="plan-extra">Extra weird $25 <span>50% off</span></label>

        <input
          type="radio"
          name="plan"
          value="regular"
          id="plan-regular"
          bind:group={plan}
        />
        <label for="plan-regular">Regular Weird <span>free</span></label>
      </div>
    </fieldset>

    <div class="register">
      <label for="username">weird name </label>
      <input
        id="username"
        bind:value={username}
        type="text"
        required
        placeholder="a [name].weird.one"
      />
      <button>
        Register
        <svg
          width="15"
          height="15"
          viewBox="0 0 15 15"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          ><path
            d="M8.14645 3.14645C8.34171 2.95118 8.65829 2.95118 8.85355 3.14645L12.8536 7.14645C13.0488 7.34171 13.0488 7.65829 12.8536 7.85355L8.85355 11.8536C8.65829 12.0488 8.34171 12.0488 8.14645 11.8536C7.95118 11.6583 7.95118 11.3417 8.14645 11.1464L11.2929 8H2.5C2.22386 8 2 7.77614 2 7.5C2 7.22386 2.22386 7 2.5 7H11.2929L8.14645 3.85355C7.95118 3.65829 7.95118 3.34171 8.14645 3.14645Z"
            fill="currentColor"
            fill-rule="evenodd"
            clip-rule="evenodd"
          ></path></svg
        >
      </button>
    </div>
  </form>

  <div class="explainers">
    <Tooltip>
      custom domains
      {#snippet content()}
        Got your own domain already? We will help you set that up after you’ve
        started your Extra subscription.
      {/snippet}
    </Tooltip>
    <Tooltip>
      Why the numbers?
      {#snippet content()}
        All new signups get four random numbers added to their account name,
        like yourname7788.weird.one We do this because Weird aspires to be a
        high-trust network that strictly minimizes inauthentic activities. The
        numerical suffix is one of several measures against anti-social behavior
        such as domain-squatting and bot registrations. <a href="https://blog.muni.town/custom-domains-for-weird/">Slightly longer answer
        here.</a>
      {/snippet}
    </Tooltip>
  </div>
</div>

<style>
  .cta {
    font-size: 1.6em;
    color: oklch(1 0 0 / 0.9);
    --border: 1px solid oklch(1 0 0 / 0.4);
  }

  form {
    display: grid;
    gap: 0.5rem;
  }

  fieldset {
    border: var(--border);
    border-radius: 2px;
    legend {
      height: 0;
      width: 0;
    }
  }

  button,
  label,
  input {
    border: 0;
    border: 0;
    padding: 1.25rem;
    margin: 0;
    color: inherit;
    background: oklch(from var(--purple) 0.2 c h / 0.7);
    backdrop-filter: blur(4px);
    font-family: "Space Mono", monospace;
  }

  .plans_toggle-content {
    display: flex;
    align-items: stretch;
    @media (max-width: 768px) {
      flex-direction: column;
    }
    input {
      position: absolute;
      width: 0;
      height: 0;
    }

    label {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: baseline;
      gap: 1.5rem;
      padding: 0.75rem 2rem;
      min-width: max-content;
      cursor: pointer;
      transition: background 160ms ease-in-out;
      span {
        padding: 1rem 1.25rem 1.125rem;
        font-size: 1.5rem;
        line-height: 50%;
        transition: border 160ms ease-in-out;
        border: var(--border);
        border-color: transparent;
        border-radius: 400px;
        background: oklch(from var(--purple) calc(l - 0.16) calc(c + 0.02) h);
        width: fit-content;
      }
      &:hover {
        background: oklch(
          from var(--purple) calc(l - 0.24) calc(c + 0.02) h / 0.8
        );
      }
      input:checked + & {
        background: oklch(from var(--purple) calc(l - 0.16) calc(c + 0.02) h);
        span {
          border: var(--border);
        }
      }
    }
  }
  .register {
    display: flex;
    border-radius: 2px;
    gap: 0;
    background: #fff4;
    border: var(--border);
  }
  label[for="username"] {
    flex: 0 1 0;
    width: 0;
    padding: 0;
    & + input {
      flex: 1 1 0;
    }
  }

  [type="text"] + button {
    padding-inline-start: 2rem;
    padding-inline-end: 1.5rem;
    background: oklch(from var(--purple) calc(l - 0.16) calc(c + 0.02) h);
    border-left: var(--border);
    display: flex;
    align-items: center;
    gap: 1rem;
    justify-content: space-between;
    svg {
      transition: transform 100ms ease-in;
    }
    &:hover svg {
      transform: translate(4px, 0px);
    }
  }

  .explainers {
    display: flex;
    justify-content: center;
    font-size: 1.3rem;
    gap: 8rem;
    padding: 1rem;
    a {
      color: inherit;
    }
  }
</style>
