<script>
	import Select from 'svelte-select';
	let Name = '';
	let Age = '';
	let items = [
		{ label: 'Austria' },
		{ label: 'Belgium' },
		{ label: 'Bulgaria' },
		{ label: 'Croatia' },
		{ label: 'Cyprus' },
		{ label: 'Czechia' },
		{ label: 'Denmark' },
		{ label: 'Estonia' },
		{ label: 'Europe non-EU (EEA/CH/UK)' },
		{ label: 'France' },
		{ label: 'Germany' },
		{ label: 'Greece' },
		{ label: 'Hungary' },
		{ label: 'Ireland' },
		{ label: 'Italy' },
		{ label: 'Latvia' },
		{ label: 'Lithuania' },
		{ label: 'Luxembourg' },
		{ label: 'Malta' },
		{ label: 'Netherlands' },
		{ label: 'Poland' },
		{ label: 'Portugal' },
		{ label: 'Romania' },
		{ label: 'Slovakia' },
		{ label: 'Spain' },
		{ label: 'Sweden' }
	];
	let selected = '';
	let excellence = '';
	let q2 = '';
	let q3 = '';
	let q4a = '';
	let q4b = '';
	let q4c = '';
	let q4d = '';
	let q4e = '';
	let q4f = '';
	let q4g = '';
	let q5 = '';
	let created = new Date();

	async function handleSubmit() {
		const data = {
			Name,
			Age,
			selected,
			excellence,
			q2,
			q3,
			q4a,
			q4b,
			q4c,
			q4d,
			q4e,
			q4f,
			q4g,
			q5,
			created
		};

		fetch(
			'https://sheet.best/api/sheets/8a267e1c-3bae-4693-b18a-f9ed9e29c7e4/tabs/Administrators',
			{
				method: 'POST',
				mode: 'cors',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify(data)
			}
		)
			.then((r) => r.json())
			.then((data) => {
				// The response comes here
				console.log(data);
			})
			.catch((error) => {
				// Errors are reported there
				console.log(error);
			});
	}
</script>

<div class="max-w-2xl">
	<form on:submit|preventDefault={handleSubmit}>
		<label>
			Name:
			<input type="text" bind:value={Name} />
		</label>

		<label>
			Age:
			<input type="text" bind:value={Age} />
		</label>

		<input id="q21" name="yes" value="10" bind:group={excellence} type="radio" />
		<label for="q21">Yes! number 10 </label>

		<label>
			<input name="yes" value="20" bind:group={excellence} type="radio" />
			No! number 20
		</label>

		<div name="question" class="mt-10 mx-5 md:ml-10">
			<p class="text-slate-500">Question 1</p>
			<h2 class="text-xl font-bold mb-5">My institution is based in the following EU country</h2>
			<Select id="countries" {items} bind:value={selected} />
		</div>

		<div name="question" class="mt-10 mx-5 md:ml-10">
			<p class="text-slate-500">Question 2</p>
			<h2 class="text-xl font-bold">
				My institution prioritizes teaching excellence in its strategic documents or discussions and
				communicates frequently about it
			</h2>
			<p class="italic text-slate-500 mb-5">
				(Frequency: 1 Never 2 Rarely 3 Occasionally 4 Frequently 5 All the time)
			</p>
			<div class="flex flex-row">
				<input type="radio" id="q11" name="q2" value="1" bind:group={q2} />
				<label for="q11">1</label>
				<input type="radio" id="q12" name="q2" value="2" bind:group={q2} />
				<label for="q12">2</label>
				<input type="radio" id="q13" name="q2" value="3" bind:group={q2} />
				<label for="q13">3</label>
				<input type="radio" id="q14" name="q2" value="4" bind:group={q2} />
				<label for="q14">4</label>
				<input type="radio" id="q15" name="q2" value="5" bind:group={q2} />
				<label for="q15">5</label>
			</div>
		</div>

		<div name="question" class="mt-10 mx-5 md:ml-10">
			<p class="text-slate-500">Question 3</p>
			<h2 class="text-xl font-bold">
				I have a clear understanding of what teaching excellence is and entails
			</h2>
			<p class="italic text-slate-500 mb-5">
				(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
			</p>
			<div class="flex flex-row">
				<input type="radio" id="q31" name="q3" value="1" bind:group={q3} />
				<label for="q31">1</label>
				<input type="radio" id="q32" name="q3" value="2" bind:group={q3} />
				<label for="q32">2</label>
				<input type="radio" id="q33" name="q3" value="3" bind:group={q3} />
				<label for="q33">3</label>
				<input type="radio" id="q34" name="q3" value="4" bind:group={q3} />
				<label for="q34">4</label>
				<input type="radio" id="q35" name="q3" value="5" bind:group={q3} />
				<label for="q35">5</label>
			</div>
		</div>

		<div name="question" class="mt-10 mx-5 md:ml-10">
			<p class="text-slate-500">Question 4</p>
			<h2 class="text-xl font-bold">To me, teaching excellence means:</h2>
			<p class="italic text-slate-500 mb-5">
				(Rank in order of priority: 1 is top priority, 7 is bottom priority)
			</p>
			<div class="flex flex-col">
				<div class="flex justify-between">
					<p for="q4a">Knowledge transfer (i.e. students mastering the subject)</p>
					<input class="border-b-4" id="q4a" placeholder="e.g. 1" type="number" bind:value={q4a} />
				</div>
				<div class="flex justify-between">
					<p for="q4b">Developing students` critical thinking</p>
					<input id="q4b" placeholder="e.g. 2" type="number" bind:value={q4b} />
				</div>

				<div class="flex justify-between">
					<p for="q4b">Developing students` lifelong learning skills</p>
					<input id="q4b" placeholder="e.g. 3" type="text" bind:value={q4c} />
				</div>
				<div class="flex justify-between">
					<p for="q4b">Developing students` relevant skills for the labour market</p>
					<input id="q4b" placeholder="e.g.4" type="text" bind:value={q4d} />
				</div>
				<div class="flex justify-between">
					<p for="q4b">Providing mentorship to students</p>
					<input id="q4b" placeholder="e.g. 5" type="text" bind:value={q4e} />
				</div>
				<div class="flex justify-between">
					<p for="q4b">Inspiring students</p>
					<input id="q4b" placeholder="e.g. 6" type="text" bind:value={q4f} />
				</div>
				<div class="flex justify-between">
					<p for="q4b">Building a sense of belonging and community</p>
					<input id="q4b" placeholder="e.g. 7" type="text" bind:value={q4g} />
				</div>
			</div>
		</div>

		<div name="question" class="mt-10 mx-5 md:ml-10">
			<p class="text-slate-500">Question 5</p>
			<h2 class="text-xl font-bold">
				I am familiar with teaching practices that promote “excellence” and I have applied some in
				my own teaching
			</h2>
			<p class="italic text-slate-500 mb-5">
				(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
			</p>
			<div class="flex flex-row">
				<input type="radio" id="q51" name="q5" value="1" bind:group={q5} />
				<label for="q51">1</label>
				<input type="radio" id="q52" name="q5" value="2" bind:group={q5} />
				<label for="q52">2</label>
				<input type="radio" id="q53" name="q5" value="3" bind:group={q5} />
				<label for="q53">3</label>
				<input type="radio" id="q54" name="q5" value="4" bind:group={q5} />
				<label for="q54">4</label>
				<input type="radio" id="q55" name="q5" value="5" bind:group={q5} />
				<label for="q55">5</label>
			</div>
		</div>

		<button class="border border-black" type="submit">Submit</button>
	</form>
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
		height: 62px;
		width: 100px;
		text-align: center;
		line-height: 62px;
		margin-right: 1em;
		border-radius: 5px;
	}
	input[type='radio']:checked + label {
		border: 2px solid black;
		background-color: black;
		color: white;
	}
	input[type='number'] {
		width: 80px;
		border: 0px solid black;
		border-bottom: solid black;
		text-align: center;
	}
</style>
