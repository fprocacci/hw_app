<script>
  import ProgressBar from "./ProgressBar.svelte";
</script>

<style>
  h2 {
    margin: 0px;
    color: red;
    align: left;
  }
  .start {
    background-color: green;
    width: 100%;
    margin: 10px 0px;
  }
</style>

<!-- <p class="">Timer</p> -->

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds Left :</h2>
</div>
<div bp="grid" />
<ProgressBar />
<div bp="grid">
  <button bp="offset-5@md 4@md 12@sm" class="start">Start</button>
</div>
