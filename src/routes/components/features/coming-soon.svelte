<script>
  import Card from "./card.svelte";
  import rawMarkdown from "./coming-soon.md?raw";
  import Markdown from "$lib/Markdown.svelte";
</script>

<Card>
  <span slot="icon">➢</span>

  <Markdown {rawMarkdown} slot="body" />
</Card>
