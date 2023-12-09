<script>
	import {Button} from '$lib/components/ui/button';
	import {isOpen} from '$lib/NavbarStore';
	import { quintInOut } from 'svelte/easing';
	import {slide} from 'svelte/transition';
</script>

<div>
	<nav class="container mx-auto p-5">
		<ul class="flex items-baseline justify-between">
			<li><a class="text-3xl font-italiana font-semibold" href="/">Aurele</a></li>
			<div class="hidden md:flex gap-4 items-baseline">
				<li><a class="font-roboto" href="/products">Products</a></li>
				<li><a class="font-roboto" href="/collections">Collections</a></li>
				<Button>
					<img width="20" height="20" src="cart.svg" alt="cart icon" />
				</Button>
			</div>
			<button
				on:click={() => isOpen.update((isOpen) => !isOpen)}
				class="material-symbols-outlined md:hidden">menu</button
			>
		</ul>
		{#if $isOpen}
			<div
				class="py-4 w-full md:hidden"
				transition:slide={{ duration: 500, easing: quintInOut, axis: 'y' }}
			>
				<ul class="flex flex-col gap-2">
					<li>
						<a
							on:click={() => isOpen.update((isOpen) => !isOpen)}
							class="block font-roboto"
							href="/products">Products</a
						>
					</li>
					<li>
						<a
							on:click={() => isOpen.update((isOpen) => !isOpen)}
							class="block font-roboto"
							href="/collections">Collections</a
						>
					</li>
				</ul>
			</div>
		{/if}
	</nav>
</div>
