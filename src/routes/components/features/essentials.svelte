<script>
  const essentials = [
    {
      title: "Digital homeownership:",
      text: [
        [
          "Every profile on Weird-net is also a website",
          "https://blog.muni.town/digital-homeownership/",
        ],
        "; use our (sub)domain or bring your own.",
      ],
    },
    {
      title: "2-minute site creation:",
      text: [
        "Escape the ",
        [
          "content-creation imperative",
          "https://blog.muni.town/content-imperative/",
        ],
        "by grabbing whatever self-links you’ve got and re-consolidate your digital identity.",
      ],
    },
    {
      title: "Reclaim your captured content:",
      text: [
        "Automated pipelines for ",
        [
          "PESOS & POSSE posting strategies",
          "https://blog.muni.town/data-defragmentation/",
        ],
        ". Write (or at least post) like ",
        ["Molly White", "https://www.mollywhite.net"],
        " and ",
        ["Cory Doctorow", "https://pluralistic.net"],
        "!",
      ],
    },
    {
      title: "Grow web gardens:",
      text: [
        "Forget about chronological web logs, we're doing ",
        [
          "digital gardening",
          "https://maggieappleton.com/nontechnical-gardening",
        ],
        " now. Casually plop your tiny blurb-seeds down and cultivate them at your leisure.",
      ],
    },
    {
      title: "Enter the indieverse:",
      text: [
        "Connect to the ",
        [
          "WWWapps Directory weird#283",
          "https://github.com/muni-town/weird/discussions/283",
        ],
        ", outside the dreary confines of big tech. 🚧Coming soon",
      ],
    },
    {
      title: "Find the others:",
      text: [
        "Participate in the ",
        [
          "chatty community gardens",
          "https://blog.muni.town/chatty-community-gardens/",
        ],
        " of ",
        ["federated webrings", "https://blog.muni.town/federated-webrings/"],
        ". 🚧Coming soon",
      ],
    },
  ];
</script>

<section>
  <div class="container">
    <h2>Essentials</h2>

    <ul>
      {#each essentials as { title, text }}
        <li>
          <p>
            <b>{title}</b>
            {#each text as t}
              {#if typeof t === "string"}
                {t}
              {:else}
                <a href={t[1]}>{t[0]}</a>
              {/if}
            {/each}
          </p>
        </li>
      {/each}
    </ul>
  </div>
</section>

<style>
  .container {
    background: var(--purple);
  }
  ul {
    display: grid;
    grid-template-columns: repeat(2, minmax(300px, max-content));
    justify-content: center;
    column-gap: 2rem;
    row-gap: 4rem;
    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }
  p {
    max-width: 60ch;
  }
  a {
    color: inherit;
  }
  h2 {
    text-align: center;
    font-size: 3em;
    padding-block-end: 6rem;
  }
</style>
