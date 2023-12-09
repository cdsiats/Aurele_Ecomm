<script>
	let showcases = [
		{
			src: './pexels-ömer-aliko-17500763-1.png',
			title: 'Spring Collection',
			description: "Embrace the season's bloom with our carefully curated array of garments"
		},
		{
			src: './pexels-boko-shots-19296212-1.png',
			title: 'Male Wardrobe',
			description: 'Explore our collection of suits, shirts, and more'
		},
		{
			src: './pexels-ge-yonk-1152077-1.png',
			title: 'Accessories',
			description: 'Complete your look with our selection of accessories'
		}
	];

	let topProducts = [
		{
			id: 1,
			src: './pexels-antony-trivet-9981968.jpg',
			title: 'Chrome Luxury Watch',
			price: '$200'
		},
		{
			id: 2,
			src: './pexels-harper-sunday-5658857.jpg',
			title: "Gold Plated Women's Bag",
			price: '$500'
		},
		{
			id: 3,
			src: './pexels-antony-trivet-12839453.jpg',
			title: 'Leather Handbag',
			price: '$350'
		},
		{
			id: 4,
			src: './pexels-andrea-piacquadio-3755706.jpg',
			title: 'Limited Edition Leather Suit',
			price: '$1200'
		}
	];
</script>

<div
	class="hero min-h-screen bg-center min-w-full"
	style="background-image: url(./pexels-antonio-bracho-19300108-1.png);"
>
	<div class="hero-overlay bg-opacity-60"></div>
	<div class="hero-content md:text-center text-neutral-content">
		<div class=" max-w-md">
			<h1 class="mb-5 text-5xl font-bold">Elevate Your Wardrobe, Elevate Your Life</h1>
			<p class="mb-5">
				Immerse yourself in the world of unparalleled craftsmanship. Our garments are meticulously
				crafted by skilled artisans who weave dreams into fabric. From the ethereal flow of our
				dresses to the precision of our tailored suits, Aurele promises an unparalleled experience.
			</p>
			<a href="/collections" class="btn btn-primary">Browse Our Collections</a>
		</div>
	</div>
</div>

<!-- Collections Section -->
<div class="p-4">
	<ul
		class="flex flex-col items-center justify-center md:flex-row flex-wrap gap-2 md:justify-around"
	>
		{#each showcases as { src, title, description }}
			<div class="card w-full md:w-96 shadow-xl image-full">
				<figure><img class="min-w-fit" {src} alt={src} /></figure>
				<div class="card-body justify-center">
					<h2 class="card-title">{title}</h2>
					<small class="text-gray-300">{description}</small>
					<div class="card-actions justify-end">
						<button class="btn btn-primary">Check it out</button>
					</div>
				</div>
			</div>
		{/each}
	</ul>
</div>

<!-- Products Showcase -->
<div class="p-6 flex flex-col items-center justify-center">
	<div class="divider">
		<p class="text-2xl font-roboto">Popular Products</p>
	</div>

	<!-- svelte-ignore a11y-invalid-attribute -->
	<div class="flex gap-4 font-roboto mt-4">
		<a class="link" href="#">All</a>
		<a href="#">Men's</a>
		<a href="#">Women's</a>
	</div>
	<div class="mt-6">
		<ul class="flex justify-around flex-wrap gap-4">
			{#each topProducts as { src, title, price, id } (id)}
				<li class="card w-64 bg-base-100 shadow-xl">
					<figure>
						<img {src} alt={src} />
					</figure>
					<div class="card-body">
						<h2 class="card-title">{title}</h2>
						<p>{price}</p>
						<div class="card-actions">
							<button class="btn btn-primary">Add to Cart</button>
						</div>
					</div>
				</li>
			{/each}
		</ul>
	</div>

	<!-- svelte-ignore a11y-invalid-attribute -->
	<div class="divider mt-10"><a class="btn btn-sm btn-outline" href="#">Load More</a></div>
</div>
