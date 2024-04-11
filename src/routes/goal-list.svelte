<script>
    import GoalItem from "./goal-item.svelte";
    export let goals = [];
</script>

<ul id="goals">
  {#each goals as goal, index (index)}
  <li>
    <GoalItem {goal} {index} on:remove={() => goals = goals.filter((_, i) => i !== index)} />
  </li>
{/each}
</ul>

<style>

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

#goals {
  margin: 2rem 0;
}

</style>