<script>
	import Hero from '$lib/components/Hero.svelte'
	import imgURL from '$lib/assets/ivan-bandura-XsAz9Mq61XY-unsplash.jpg'
</script>

<Hero {imgURL} overlay id="welcome">
	{#snippet heading()}
		<h1 class="animate-fly-up-slow">
			Filling Southern MN with healthy churches
			<a href="#imaginary-1" class="font-bold">for the next 100 years.</a>
		</h1>
	{/snippet}
</Hero>

<Hero id="imaginary-1">
	{#snippet heading()}
		<h1>Jesus is decidedly unstrategic.</h1>
	{/snippet}
	{#snippet body()}
		<p>
			He came to the sound of angels singing and then spent the next thirty years learning
			carpentry. Even during his public ministry, he spent most of his time going at a slow pace in
			a small place. This is unstrategic not because there was no plan, but because the plan doesn’t
			make sense! Yet the madness of this plan is exactly how God chose to display the upside-down
			nature of his Kingdom. Jesus won by dying. Jesus chose two women to witness the resurrection.
			Jesus built his church on the preaching of one of his betrayers. Jesus' plan is beautiful—but
			mad. <a href="#imaginary-2">Believing it takes imagination.</a>
		</p>
	{/snippet}
</Hero>

<Hero id="imaginary-2">
	{#snippet heading()}
		<h1>Many view rural ministry as unstrategic.</h1>
	{/snippet}
	{#snippet body()}
		<p>
			Yet we believe rural ministry presents a unique opportunity to display the very upside-down
			gospel we proclaim. Going at a slow pace in a small place as we win by dying embodies the
			gospel logic of John 12:24:
			<em>
				“Truly, truly, I say to you, unless a grain of wheat falls into the earth and dies, it
				remains alone; but if it dies, it bears much fruit."
			</em>
			The slowness and smallness of this kind of ministry requires a certain kind of
			<strong>gospel imaginary</strong>
			from those who pastor here. It’s the kind of imaginary Wendell Berry calls for in his poem
			<em>Manifesto: The Mad Farmer Liberation Front:</em>
		</p>
		<pre>So, friends, every day do something
that won’t compute....
Invest in the millennium. Plant sequoias.
Say that your main crop is the forest
that you did not plant,
that you will not live to harvest.</pre>
		<p>
			We’ve caught this madness. And out of this gospel madness flows <a href="#vision"
				>our 100 year vision.</a
			>
		</p>
	{/snippet}
</Hero>
