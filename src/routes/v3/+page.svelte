<script>
	import Select from 'svelte-select';

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
	let q6a = '';
	let q6b = '';
	let q6c = '';
	let q6d = '';
	let q6e = '';
	let q6f = '';
	let q6g = '';
	let q6h = '';
	let q7a = '';
	let q7b = '';
	let q7c = '';
	let q7d = '';
	let q7e = '';
	let q7f = '';
	let q7g = '';
	let q7h = '';
	let q7i = '';
	let q7j = '';
	let q7k = '';
	let q9 = '';
	let q10 = '';
	let q11 = '';
	let q12 = '';
	let email = '';

	let created = new Date();

	async function handleSubmit() {
		const data = {
			selected,
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
			q6a,
			q6b,
			q6c,
			q6d,
			q6e,
			q6f,
			q6g,
			q6h,
			q7a,
			q7b,
			q7c,
			q7d,
			q7e,
			q7f,
			q7g,
			q7h,
			q7i,
			q7j,
			q7k,
			q9,
			q10,
			q11,
			q12,
			email,

			created
		};

		fetch('https://sheet.best/api/sheets/8a267e1c-3bae-4693-b18a-f9ed9e29c7e4/tabs/Rawa', {
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
	}
</script>

<div class="flex justify-center">
	<div class="max-w-xl">
		<img src="/enote-logo.png" />
		<form on:submit|preventDefault={handleSubmit}>
			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 1</p>
				<h2 class="text-xl font-bold mb-5">My institution is based in the following EU country</h2>
				<Select id="countries" {items} bind:value={selected} />
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 2</p>
				<h2 class="text-xl font-bold">
					My institution prioritizes teaching excellence in its strategic documents or discussions
					and communicates frequently about it
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Frequency: 1 Never 2 Rarely 3 Occasionally 4 Frequently 5 All the time)
				</p>
				<div class="flex flex-row justify-between">
					<input class="hidden" type="radio" id="q11" name="q2" value="1" bind:group={q2} />
					<label for="q11">1</label>
					<input class="hidden" type="radio" id="q12" name="q2" value="2" bind:group={q2} />
					<label for="q12">2</label>
					<input class="hidden" type="radio" id="q13" name="q2" value="3" bind:group={q2} />
					<label for="q13">3</label>
					<input class="hidden" type="radio" id="q14" name="q2" value="4" bind:group={q2} />
					<label for="q14">4</label>
					<input class="hidden" type="radio" id="q15" name="q2" value="5" bind:group={q2} />
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
					(Rank in order of priority: 1 is the top priority, 7 is the bottom priority)
				</p>
				<div class="flex flex-col">
					<div class="flex justify-between">
						<p for="q4a">Knowledge transfer (i.e. students mastering the subject)</p>
						<input
							class="border-b-4"
							id="q4a"
							placeholder="e.g. 1"
							type="number"
							bind:value={q4a}
						/>
					</div>
					<div class="flex justify-between">
						<p for="q4b">Developing students` critical thinking</p>
						<input id="q4b" placeholder="e.g. 2" type="number" bind:value={q4b} />
					</div>

					<div class="flex justify-between">
						<p for="q4b">Developing students` lifelong learning skills</p>
						<input id="q4b" placeholder="e.g. 3" type="number" bind:value={q4c} />
					</div>
					<div class="flex justify-between">
						<p for="q4b">Developing students` relevant skills for the labour market</p>
						<input id="q4b" placeholder="e.g. 4" type="number" bind:value={q4d} />
					</div>
					<div class="flex justify-between">
						<p for="q4b">Providing mentorship to students</p>
						<input id="q4b" placeholder="e.g. 5" type="number" bind:value={q4e} />
					</div>
					<div class="flex justify-between">
						<p for="q4b">Inspiring students</p>
						<input id="q4b" placeholder="e.g. 6" type="number" bind:value={q4f} />
					</div>
					<div class="flex justify-between">
						<p for="q4b">Building a sense of belonging and community</p>
						<input id="q4b" placeholder="e.g. 7" type="number" bind:value={q4g} />
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

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 6</p>
				<h2 class="text-xl font-bold">
					In my opinion the most important qualities of an excellent teacher are:
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Rank in order of priority: 1 is the top priority, 8 is the bottom priority)
				</p>
				<div class="flex flex-col">
					<div class="flex justify-between">
						<p for="q6a">Having in-depth knowledge of the subject</p>
						<input
							class="border-b-4"
							id="q6a"
							placeholder="e.g. 1"
							type="number"
							bind:value={q6a}
						/>
					</div>
					<div class="flex justify-between">
						<p for="q6b">An active research profile on the subject taught</p>
						<input id="q6b" placeholder="e.g. 2" type="number" bind:value={q6b} />
					</div>
					<div class="flex justify-between">
						<p for="q6c">Being a scholar of teaching and learning</p>
						<input id="q6c" placeholder="e.g. 3" type="number" bind:value={q6c} />
					</div>
					<div class="flex justify-between">
						<p for="q6d">Being an effective communicator</p>
						<input id="q6d" placeholder="e.g. 4" type="number" bind:value={q6d} />
					</div>
					<div class="flex justify-between">
						<p for="q6e">Being empathetic</p>
						<input id="q6e" placeholder="e.g. 5" type="number" bind:value={q6e} />
					</div>
					<div class="flex justify-between">
						<p for="q6f">Being confident</p>
						<input id="q6f" placeholder="e.g. 6" type="number" bind:value={q6f} />
					</div>
					<div class="flex justify-between">
						<p for="q6g">Being open-minded</p>
						<input id="q6g" placeholder="e.g. 7" type="number" bind:value={q6g} />
					</div>
					<div class="flex justify-between">
						<p for="q6h">Being organised</p>
						<input id="q6h" placeholder="e.g. 8" type="number" bind:value={q6h} />
					</div>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 7</p>
				<h2 class="text-xl font-bold">
					In my opinion the conditions that contribute most significantly to teaching excellence
					are:
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Rank in order of priority: 1 is the top priority, 11 is the bottom priority)
				</p>
				<div class="flex flex-col">
					<div class="flex justify-between">
						<p for="q7a">Financial resources</p>
						<input id="q7a" placeholder="e.g. 1" type="number" bind:value={q7a} />
					</div>
					<div class="flex justify-between">
						<p for="q6b">Time allocation</p>
						<input id="q6b" placeholder="e.g. 2" type="number" bind:value={q7b} />
					</div>
					<div class="flex justify-between">
						<p for="q6c">Excellent facilities</p>
						<input id="q6c" placeholder="e.g. 3" type="number" bind:value={q7c} />
					</div>
					<div class="flex justify-between">
						<p for="q6d">Support from university management</p>
						<input id="q6d" placeholder="e.g. 4" type="number" bind:value={q7d} />
					</div>
					<div class="flex justify-between">
						<p for="q6e">Innovation and experimentation</p>
						<input id="q6e" placeholder="e.g. 5" type="number" bind:value={q7e} />
					</div>
					<div class="flex justify-between">
						<p for="q6f">Staff training</p>
						<input id="q6f" placeholder="e.g. 6" type="number" bind:value={q7f} />
					</div>
					<div class="flex justify-between">
						<p for="q6g">Feedback from students</p>
						<input id="q6g" placeholder="e.g. 7" type="number" bind:value={q7g} />
					</div>
					<div class="flex justify-between">
						<p for="q6h">Feedback from peers</p>
						<input id="q6h" placeholder="e.g. 8" type="number" bind:value={q7h} />
					</div>
					<div class="flex justify-between">
						<p for="q6h">Feedback from accreditation bodies/quality assurance bodies</p>
						<input id="q6h" placeholder="e.g. 9" type="number" bind:value={q7i} />
					</div>
					<div class="flex justify-between">
						<p for="q6h">Teaching awards</p>
						<input id="q6h" placeholder="e.g. 10" type="number" bind:value={q7j} />
					</div>
					<div class="flex justify-between">
						<p for="q6h">Teaching-focused career paths/promotions</p>
						<input id="q6h" placeholder="e.g. 11" type="number" bind:value={q7k} />
					</div>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 9</p>
				<h2 class="text-xl font-bold">
					Excellent teaching is important for promotion at my institution
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
				</p>
				<div class="flex flex-row">
					<input type="radio" id="q91" name="q9" value="1" bind:group={q9} />
					<label for="q91">1</label>
					<input type="radio" id="q92" name="q9" value="2" bind:group={q9} />
					<label for="q92">2</label>
					<input type="radio" id="q93" name="q9" value="3" bind:group={q9} />
					<label for="q93">3</label>
					<input type="radio" id="q94" name="q9" value="4" bind:group={q9} />
					<label for="q94">4</label>
					<input type="radio" id="q95" name="q9" value="5" bind:group={q9} />
					<label for="q95">5</label>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 10</p>
				<h2 class="text-xl font-bold">
					There are sufficient awards and recognition schemes for excellent teaching at my
					institution
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
				</p>
				<div class="flex flex-row">
					<input type="radio" id="q101" name="q10" value="1" bind:group={q10} />
					<label for="q101">1</label>
					<input type="radio" id="q102" name="q10" value="2" bind:group={q10} />
					<label for="q=102">2</label>
					<input type="radio" id="q103" name="q10" value="3" bind:group={q10} />
					<label for="q103">3</label>
					<input type="radio" id="q104" name="q10" value="4" bind:group={q10} />
					<label for="q104">4</label>
					<input type="radio" id="q105" name="q10" value="5" bind:group={q10} />
					<label for="q105">5</label>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 11</p>
				<h2 class="text-xl font-bold">
					My institution offers a sufficient number of trainings for improving my teaching
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
				</p>
				<div class="flex flex-row">
					<input type="radio" id="q111" name="q11" value="1" bind:group={q11} />
					<label for="q111">1</label>
					<input type="radio" id="q112" name="q11" value="2" bind:group={q11} />
					<label for="q112">2</label>
					<input type="radio" id="q113" name="q11" value="3" bind:group={q11} />
					<label for="q113">3</label>
					<input type="radio" id="q114" name="q11" value="4" bind:group={q11} />
					<label for="q114">4</label>
					<input type="radio" id="q115" name="q11" value="5" bind:group={q11} />
					<label for="q115">5</label>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 12</p>
				<h2 class="text-xl font-bold">
					I have attended training courses on teaching skills in the past
				</h2>
				<p class="italic text-slate-500 mb-5">
					(Agreement: 1 Strongly Disagree 2 Disagree 3 Undecided 4 Agree 5 Strongly Agree)
				</p>
				<div class="flex flex-row">
					<input type="radio" id="q121" name="q12" value="1" bind:group={q12} />
					<label for="q121">1</label>
					<input type="radio" id="q122" name="q12" value="2" bind:group={q12} />
					<label for="q122">2</label>
					<input type="radio" id="q123" name="q12" value="3" bind:group={q12} />
					<label for="q123">3</label>
					<input type="radio" id="q124" name="q12" value="4" bind:group={q12} />
					<label for="q124">4</label>
					<input type="radio" id="q125" name="q12" value="5" bind:group={q12} />
					<label for="q125">5</label>
				</div>
			</div>

			<div name="question" class="mt-10 mx-5 md:ml-10">
				<p class="text-slate-500">Question 13</p>
				<h2 class="text-xl font-bold">What's your email address:</h2>
				<input class="w-full" type="email" bind:value={email} />
			</div>
			<button
				class="border border-black my-20 font-bold mx-5 md:ml-10 w-full h-12 text-white bg-black"
				type="submit">Show me how I compare to others</button
			>
		</form>

		<div name="comps">
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 2: My institution prioritizes teaching excellence in its strategic documents or
					discussions and communicates frequently about it
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q2}.</span> The European average is 3.7
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 3: I have a clear understanding of what teaching excellence is and entails
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q3}.</span> The European average is 3.9
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 5: I am familiar with teaching practices that promote “excellence” and I have
					applied some in my own teaching
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q5}.</span> The European average is 3.6
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 9: Excellent teaching is important for promotion at my institution
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q9}.</span> The European average is 3.0
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 10: There are sufficient awards and recognition schemes for excellent teaching at
					my institution
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q10}.</span> The European average is 2.6
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 11: My institution offers a sufficient number of trainings for improving my
					teaching
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q11}.</span> The European average is 3.1
				</p>
			</div>
			<div class="max-w-2x mt-10 mx-5 md:ml-10">
				<h2 class="text-xl font-bold mb-2">
					Question 12: I have attended training courses on teaching skills in the past
				</h2>
				<p class="text-xl">
					You selected <span class="font-bold">{q12}.</span> The European average is 3.3
				</p>
			</div>
			<div class="h-32" />
		</div>
	</div>
</div>

<style>
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
		width: 90px;
		border: 0px solid black;
		border-bottom: solid black;
		text-align: center;
	}
	input[type='email'] {
		width: 100%;
		border: 0px solid black;
		border-bottom: solid black;
		text-align: center;
	}
</style>
