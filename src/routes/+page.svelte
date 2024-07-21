<script lang='ts'>
	import { videoLink } from '../stores.js';
	import { goto } from '$app/navigation';

	let inputLink = '';

	const handleSubmit = () => {
	videoLink.set(inputLink);
	goto('/transcription');
	};

	const handleKeydown = (event: KeyboardEvent) => {
		if (event.key === 'Enter') {
		handleSubmit();
		}
	};
</script>

<div class="flex flex-col items-center justify-center min-h-screen bg-gray-100">
	<p class="text-4xl text-center mt-2 font-light text-gray-500">
		Fact check videos using AI
	</p>
	<div class="display: flex; justify-content: center; align-items: center; height: 100vh;">
		<img src='/Verif.ai.svg' alt="Verif.ai Logo" class="logo w-68 h-68"/>
	</div>
	<div class="mt-4 w-full max-w-md flex justify-center">
		<label class="input input-bordered flex items-center gap-2">
		  <input 
			type="text" 
			class="grow" 
			placeholder="Paste YouTube link" 
			bind:value={inputLink}
			on:keydown={handleKeydown}
		  />
		  <kbd class="kbd kbd-sm">Enter</kbd>
		</label>
	  </div>
</div>