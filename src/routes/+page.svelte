<script lang="ts">
	import { fade } from 'svelte/transition';

	let selected = 0;

	let currentAge = Math.floor((Date.now() - new Date('2007-06-07').getTime()) / 31556952000);
</script>

<div class="min-h-screen w-full bg-neutral-300">
	<div class="absolute bottom-0 left-0 w-full">
		<div
			class="text-[25vw] lg:text-[20vw] pb-8 text-neutral-800 font-medium leading-none select-none"
		>
			peony
		</div>
		<div
			class={`w-full ${
				selected != 0 ? 'h-96 text-[5vw] lg:text-[2vw]' : 'h-48 text-[8vw] lg:text-[3vw]'
			} bg-neutral-800 p-4 flex-col gap-8 text-neutral-300 z-10 transition-all duration-500 ease-in-out`}
			on:mouseleave={() => {
				selected = 0;
			}}
			role="none"
		>
			<div class="flex gap-8 pb-8 select-none">
				<button
					class="h-min hover:text-neutral-500 transition duration-500 ease-in-out"
					on:click={() => {
						selected = 1;
					}}>projects</button
				>
				<button
					class="h-min hover:text-neutral-500 transition duration-500 ease-in-out"
					on:click={() => {
						selected = 2;
					}}>info</button
				>
				<button
					class="h-min hover:text-neutral-500 transition duration-500 ease-in-out"
					on:click={() => {
						selected = 3;
					}}>socials</button
				>
			</div>

			{#if selected == 1}
				<div
					in:fade={{ duration: 300, delay: 200 }}
					out:fade={{ duration: 300 }}
					class="text-3xl text-neutral-400 flex-col flex gap-2"
				>
					<h2 class="text-4xl text-neutral-300 font-medium pb-4">projects</h2>
					<a
						href="https://omegabot.shop/"
						class="underline hover:text-neutral-500 transition duration-500 ease-in-out">omegabot</a
					>
					<a
						href="https://github.com/peonii/moonstone"
						class="underline hover:text-neutral-500 transition duration-500 ease-in-out"
						>moonstone</a
					>
				</div>
			{:else if selected == 2}
				<div
					in:fade={{ duration: 300, delay: 350 }}
					out:fade={{ duration: 300 }}
					class="text-3xl text-neutral-400 flex-col flex gap-2"
				>
					<h2 class="text-4xl text-neutral-300 font-medium pb-4">info</h2>
					<div>pronouns - she/her</div>
					<div>age - {currentAge}</div>
					<div>location - poland</div>
					<div>fav langs - rust, go, elixir</div>
				</div>
			{:else if selected == 3}
				<div
					in:fade={{ duration: 300, delay: 350 }}
					out:fade={{ duration: 300 }}
					class="text-3xl text-neutral-400 flex-col flex gap-2"
				>
					<h2 class="text-4xl text-neutral-300 font-medium pb-4">socials</h2>
					<div
						class="hover:text-neutral-500 transition duration-500 ease-in-out cursor-pointer"
						on:click={() => {
							navigator.clipboard.writeText('peony');
						}}
						role="none"
					>
						discord (click to copy)
					</div>
					<a
						class="hover:text-neutral-500 transition duration-500 ease-in-out cursor-pointer"
						href="https://github.com/peonii">github</a
					>
					<a
						class="hover:text-neutral-500 transition duration-500 ease-in-out cursor-pointer"
						href="https://youtube.com/@peony6666">youtube</a
					>
				</div>
			{/if}
		</div>
	</div>
</div>
