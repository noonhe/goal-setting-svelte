<script>
  import goals from '../goals.json'
  import { createEventDispatcher } from 'svelte';



const dispatch = createEventDispatcher();
let newGoal = '';
 
const submitGoal = (event) => {
  if (newGoal.trim()) {
    goals.push({"id": `${new Date().getTime()}` , "title": newGoal});
    dispatch('add');
    newGoal = ''; // Clear input after submission
  }
}
</script>


<form id="goal-form" on:submit|preventDefault={submitGoal}>
    <div>
      <label for="goal">Goal</label>
      <input bind:value={newGoal} type="text" id="goal" name="goal" />
    </div>
    <button  type="submit">Add goal</button>
</form>


<style>
    form {
  display: flex;
  gap: 1rem;
  align-items: flex-end;
}

form label {
  display: block;
  font-weight: bold;
  color: #2b292e;
  font-size: 0.9rem;
  margin-right: 0.25rem;
  margin-bottom: 0.25rem;
}

form input {
  font: inherit;
  border: none;
  background-color: #f4f2f7;
  color: #151416;
  padding: 0.5rem 0.25rem;
  width: 20rem;
  border-radius: 4px;
}

form button {
  font: inherit;
  padding: 0.5rem 1rem;
  border: none;
  background-color: #35056b;
  color: white;
  border-radius: 4px;
}

form button:hover,
form button:active {
  background-color: #4c0899;
}

form button:disabled{
  background-color: gray;
}

</style>