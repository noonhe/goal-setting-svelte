<script>
import GoalForm from "./goal-form.svelte";
import GoalList from "./goal-list.svelte";
import goals from '../goals.json'
let myGoals = [...goals];

// async function loadGoals() {
//     const response = await fetch('goals.json');
//     myGoals = await response.json();
// }

// loadGoals();

</script>

<section>
    <GoalForm on:add={() => myGoals= [...goals]}/>
</section>
<section>
    <GoalList goals={myGoals} />
</section>

<style>

</style>