<div class="cta">
  <form action="post">
    <div class="cta-plans">
      <button>Extra weird $25 <span>50% off</span></button>
      <button>Regular Weird <span>free</span></button>
    </div>

    <div class="cta-register">
      <input type="text" placeholder="a [name].weird.one" />
      <button>Register</button>
    </div>
  </form>

  <div class="explainers">
    <a href="a">custom domains</a><a href="b">Why the numbers?</a>
  </div>
</div>

<style>
  button {
    background: transparent;
    border: 0;
    min-width: max-content;
    padding: .75rem 2rem;
    min-width: max-content;
  }
  form {
    display: grid;
    gap: .5rem;
  }
  .cta-plans {
    display: flex;
    background: blue;
    padding: 0.25rem;
    border: 1px solid white;
    background: #fff4;
    align-items: center;

    button {
      display: flex;
      gap: 2rem;
      align-items: center;
      span {
        padding: 0.5rem 2rem;
        background: var(--purple);
        border: 1px solid transparent;
        border-radius: 400px;
        width: fit-content;
      }
      &:hover {
        background: var(--purple);
        span {
          border-color: white;
        }
      }
    }
  }
  .cta-register {
    display: flex;
    gap: 0;
    background: #fff4;
    border: 1px solid white;
    input {
      flex: 1 1 0;
      padding: 1.25rem 3rem;
      border: 0;
      border-radius: 0;
      background: transparent;
    }
    button {
      padding-inline: 3rem;
      background: var(--purple);
      border-left: 1px solid white;
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
