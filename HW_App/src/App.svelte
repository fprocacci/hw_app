<script>
	import Timer from "./Timer.svelte";
	import HowTo from "./HowTo.svelte";
	let audio;

	function timerEnds(e) {
		console.log(e);
		audio.play();
	}
</script>

<style>
	h1,
	h3 {
		text-align: center;
	}
</style>

<h1>Handwashing App</h1>

<Timer on:end={timerEnds} />
<HowTo />

<h3>
	<!-- This url doesn't exist on Dec 20, 2020 at 1151 -->
	<a
		href="https://www.who.int/docs/default-source/patient-safety/how-to-handwash-poster.pdf?sfvrsn=7004a09d_2">Picture
		Source</a>

	<a href="https://freesound.org/people/metrostock99/sounds/345086/">Sound
		Source</a>
</h3>

<!-- <audio src="short_sound.wav" /> -->

<audio bind:this={audio}>
	<source src="short_sound.wav" />
</audio>
