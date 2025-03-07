<script lang="ts">
	import { onMount } from 'svelte';
	import { Tween } from 'svelte/motion';

	let { children } = $props();

	let element: HTMLElement;

	const opacity = new Tween(0, {
		duration: 700
	});

	const handleIntersection = (entries: IntersectionObserverEntry[]) => {
		entries.forEach((entry) => {
			if (entry.isIntersecting) {
				opacity.set(1);
			} else {
				opacity.set(0);
			}
		});
	};

	let observer: IntersectionObserver;

	onMount(() => {
		$effect(() => {
			observer = new IntersectionObserver(handleIntersection, {
				threshold: 0.1
			});

			observer.observe(element);

			return () => {
				observer.disconnect();
			};
		});
	});
</script>

<div bind:this={element} style:opacity={opacity.current}>
	{@render children()}
</div>
