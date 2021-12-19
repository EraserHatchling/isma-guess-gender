<script>
    let userName = "";
    let userGender = "";
async function getGender() {
  fetch('https://api.genderize.io/?name=' + userName)
	.then((response) => response.json())
	.then((data) => {
  	userName = data.name; 
  	userGender = data.gender; 
	});
}
</script>

<h1>Guess Gender App</h1>

<form on:submit|preventDefault={getGender}>
    <label for="name">Name:</label>
    <input id="userName" bind:value={userName} type="text" />
    <button type="submit">Check</button>
</form>
<p>Gender:{userGender}</p>
