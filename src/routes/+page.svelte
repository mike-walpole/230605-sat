<script>
	import { Radio } from 'flowbite-svelte';
	import { ButtonGroup, Button } from 'flowbite-svelte';
	let aaa = 10;
	let bbb = [];
	let ccc = [];
	$: ddd = (-(-scoops - innov) / 10) * 100;
	let selected = '20';
	import { Range, Label } from 'flowbite-svelte';
	let minmaxValue = 0;
	let two = 3;
	let three = 3;

	function onChange(event) {
		selected = event.currentTarget.value;
	}

	let scoops = 1;
	let innov = 1;
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>{aaa}</p>

<form>
	<radio> Option 1 Optiion 2 </radio>
	<input bind:value={bbb} />
	<input bind:value={ccc} />
</form>

<div>
	<h2>INNOVATION</h2>
	<h3>your innovation score measures how innovative is you institution</h3>
	<h1>{ddd}%</h1>
	<p class="text-3xl">the European average score is 47%</p>
</div>

<p class="mb-4 font-semibold text-gray-900 dark:text-white">Identification</p>
<ul
	class="items-center w-full rounded-lg border border-gray-200 sm:flex dark:bg-gray-800 dark:border-gray-600 divide-x divide-gray-200 dark:divide-gray-600"
>
	<li class="w-full"><Radio name="hor-list" class="p-3 mr-3">Never</Radio></li>
	<li class="w-full"><Radio name="hor-list" class="p-3">Rarely</Radio></li>
	<li class="w-full"><Radio name="hor-list" class="p-3">Sometimes</Radio></li>
	<li class="w-full"><Radio name="hor-list" class="p-3">Often</Radio></li>
	<li class="w-full"><Radio name="hor-list" class="p-3">Always</Radio></li>
</ul>

<div class="grid grid-cols-2 gap-6">
	<div class="rounded border border-gray-200 dark:border-gray-700">
		<Radio name="bordered" class="w-full p-4">Default radio</Radio>
	</div>
	<div class="rounded border border-gray-200 dark:border-gray-700">
		<Radio name="bordered" class="w-full p-4">Checked state</Radio>
	</div>
</div>

<ButtonGroup class="mb-10">
	<Button outline color="dark active:bg-black">Profile</Button>
	<Button outline color="dark">Settings</Button>
	<Button outline color="dark">Messages</Button>
</ButtonGroup>

<p class="my-10">first question</p>
<label class="border border-black rounded-md p-5 mr-3 checked:bg-violet-500">
	<input type="radio" group={scoops} name="scoops" value={1} />
	One scoop
</label>

<label class="border border-black rounded-md p-5 mr-3 focus:ring-red-200">
	<input type="radio" group={scoops} name="scoops" value={2} />
	Two scoops
</label>

<label class="border border-black rounded-md p-5 mr-3">
	<input class="border border-black" type="radio" group={scoops} name="scoops" value={3} />
	Three scoops
</label>

<p class="my-10">second question</p>

<label class="border border-black rounded-md p-5 mr-3">
	<input type="radio" group={innov} name="innov" value={1} />
	One scoop
</label>

<div class="w-1/2">
	<Label>Min-max range</Label>
	<Range id="range-minmax" min="1" max="5" bind:value={minmaxValue} />
	<p>You've selectred: {minmaxValue}. The European Average is 3.4</p>
</div>

<div class="w-1/2">
	<Label>Min-max range</Label>
	<Range id="range-minmax" min="1" max="5" bind:value={two} />
	<p>You've selectred: {two}. The European Average is 3.4</p>
</div>

<div class="w-1/2">
	<Label>Min-max range</Label>
	<Range id="range-minmax" min="1" max="5" bind:value={three} />
	<p>You've selectred: {three}. The European Average is 3.4</p>
</div>

<button class="bg-violet-200 hover:bg-violet-400 active:bg-violet-600"> click me </button>

<input type="radio" class="bg-red-100 border-red-300 text-red-500 focus:ring-red-200" />

<input type="email" class="form-input px-4 py-3 rounded-full" />

<input id="banana" type="radio" name="quiz" value="banana" />
<label for="banana">Banana</label>
<input id="apple" type="radio" name="quiz" value="apple" />
<label for="apple">Apple</label>
<input id="strawberry" type="radio" name="quiz" value="strawberry" />
<label for="strawberry">Strawberry</label>
<input id="orange" type="radio" name="quiz" value="orange" />
<label for="orange">Orange</label>

<a href="/v3" class="button border border-black"> Contact Us </a>

<style>
	input[type='radio'] {
		display: none;
	}
	input[type='radio'] + label {
		border: 5px solid lightblue;
		background-color: lightblue;
		cursor: pointer;
		display: block;
		height: 40px;
		width: 200px;
		text-align: center;
		line-height: 40px;
	}
	input[type='radio']:checked + label {
		border: 5px solid blue;
		background-color: dodgerblue;
	}
</style>
