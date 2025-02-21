<script>
  const essentials = [
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  { title: "Digital Ownership", text: [] },
  ];
</script>

<section>
  <div class="container">
    <h2>Essentials</h2>

    <ul>
      {#each essentials as { title, text }}
        <li>
          <p>
            <b>{title}</b> <a> Every so often</a>use our
          </p>
        </li>
      {/each}
    </ul>
  </div>
</section>

<style>
ul {
  display: grid;  
  grid-template-columns: 1fr 1fr;
  gap:2rem;
}
</style>
