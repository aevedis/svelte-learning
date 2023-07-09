<script>
  import Counter from "./lib/Counter.svelte";

  const props = {
        maxCount: 15,
    initialCount: 0
  }
</script>

<Counter {...props} />