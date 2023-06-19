<script>
	let selected = '';
	let selected2 = '';
	let q1 = 0;
	function onChange(event) {
		selected = event.currentTarget.value;
	}
	function onChange2(event) {
		selected2 = event.currentTarget.value;
	}
	let user = {
		ageRange: 0
	};
	const data = {
		Id: [selected],
		Name: [selected2],
		Age: [q1],
		'Created at': new Date()
	};

	// Add one line to the sheet
	fetch('https://sheet.best/api/sheets/8a267e1c-3bae-4693-b18a-f9ed9e29c7e4/tabs/Academics', {
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

<form class="pure-form">
	<div class="flex flex-row mb-10">
		<input id="banana" type="radio" name="quiz" on:change={() => (q1 += 1)} />
		<label for="banana">Never</label>
		<input id="apple" type="radio" name="quiz" on:change={() => (q1 += 2)} />
		<label for="apple">Rarely</label>
		<input id="strawberry" type="radio" name="quiz" on:change={() => (q1 += 3)} />
		<label for="strawberry">Occasionally</label>
		<input id="orange" type="radio" name="quiz" on:change={() => (q1 += 4)} />
		<label for="orange">Frequently</label>
		<input id="orange2" type="radio" name="quiz" on:change={() => (q1 += 5)} />
		<label for="orange2">All the time</label>
	</div>

	<p>how often do you review stuff</p>
	<div class="flex flex-row">
		<input id="banana1" type="radio" name="quiz1" on:change={onChange} value="1" />
		<label for="banana1">one</label>
		<input id="apple1" type="radio" name="quiz1" on:change={onChange} value="2" />
		<label for="apple1">two</label>
		<input id="strawberry1" type="radio" name="quiz1" on:change={onChange} value="3" />
		<label for="strawberry1">three</label>
		<input id="orange1" type="radio" name="quiz1" on:change={onChange} value="4" />
		<label for="orange1">four</label>
	</div>
	<button type="submit">submit</button>

	<p>Q3 how often do you review stuff</p>
	<div class="flex flex-row">
		<input id="banana2" type="radio" name="quiz2" on:change={onChange2} value="1" />
		<label for="banana2">one</label>
		<input id="apple2" type="radio" name="quiz2" on:change={onChange2} value="2" />
		<label for="apple2">two</label>
		<input id="strawberry2" type="radio" name="quiz2" on:change={onChange2} value="3" />
		<label for="strawberry2">three</label>
		<input id="orange3" type="radio" name="quiz2" on:change={onChange2} value="4" />
		<label for="orange3">four</label>
	</div>
	<button type="submit">submit</button>
</form>

<p>Q1: {q1}</p>
<p>Q2: {selected}</p>
<p>Q3: {selected2}</p>

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
