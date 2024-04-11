<script>
    import { createEventDispatcher } from 'svelte';

    export let goal;
    export let index;

    const dispatch = createEventDispatcher();

    function removeGoal() {
    dispatch('remove');
    }
</script>
  
  <li>
    <span>
        {goal.title}
    </span>
    <button on:click={removeGoal}>Remove</button>
  </li>

  <style>

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  margin: 0.5rem 0;
  background-color: #272529;
  color: #e8e4ed;
  border-radius: 6px;
  box-shadow: 0 0 6px rgba(0, 0, 0, 0.3);
}

li span {
  font-weight: bold;
}

li button {
  font: inherit;
  padding: 0.5rem 1rem;
  border: none;
  background-color: #f667af;
  color: #141213;
  border-radius: 4px;
}
li button:hover,
li button:active {
  background-color: #f6459d;
}
  </style>