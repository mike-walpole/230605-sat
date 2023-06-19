<script>
	const data = {
		Id: 10,
		Name: 'Jane Doe',
		Age: 13,
		'Created at': new Date()
	};

	// Add one line to the sheet
	fetch('https://sheet.best/api/sheets/8a267e1c-3bae-4693-b18a-f9ed9e29c7e4', {
		method: 'POST',
		mode: 'cors',
		headers: {
			'Content-Type': 'application/json'
		},
		body: JSON.stringify(data)
	})
		.then((r) => r.json())
		.then((data) => {
			// The response comes here
			console.log(data);
		})
		.catch((error) => {
			// Errors are reported there
			console.log(error);
		});
</script>

<div class="flex flex-row mb-10">
	<input id="banana" type="radio" name="quiz" value="1" />
	<label for="banana">Banana</label>
	<input id="apple" type="radio" name="quiz" value="2" />
	<label for="apple">Apple</label>
	<input id="strawberry" type="radio" name="quiz" value="3" />
	<label for="strawberry">Strawberry</label>
	<input id="orange" type="radio" name="quiz" value="4" />
	<label for="orange">Orange</label>
</div>

<p>how often do you review stuff</p>
<div class="flex flex-row">
	<input id="banana1" type="radio" name="quiz1" value="1" />
	<label for="banana1">one</label>
	<input id="apple1" type="radio" name="quiz1" value="2" />
	<label for="apple1">two</label>
	<input id="strawberry1" type="radio" name="quiz1" value="3" />
	<label for="strawberry1">three</label>
	<input id="orange1" type="radio" name="quiz1" value="4" />
	<label for="orange1">four</label>
</div>

<style>
	input[type='radio'] {
		display: none;
	}
	input[type='radio'] + label {
		border: 2px solid black;
		background-color: white;
		cursor: pointer;
		display: block;
		height: 40px;
		width: 200px;
		text-align: center;
		line-height: 40px;
		margin-right: 1em;
	}
	input[type='radio']:checked + label {
		border: 2px solid black;
		background-color: black;
		color: white;
	}
</style>
