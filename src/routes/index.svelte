<script>
    let name = ''
    let age = ''

    async function getAge() {
        fetch('https://api.agify.io/?name=' + name)
        .then((response) => response.json())
        .then((data) => {
  	age = data.age; // Path for age
	});
}
</script>

<h1>Guess Age</h1>

<form on:submit|preventDefault={getAge}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>

<p>Age: {age}</p>


