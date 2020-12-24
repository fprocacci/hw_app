<script>
  import { createEventDispatcher } from "svelte";
  import ProgressBar from "./ProgressBar.svelte";

  let totalSeconds = 20;
  let secondsLeft = totalSeconds;
  let isRunning = false;
  //$: progress = ((totalSeconds - secondsLeft) / totalSeconds) * 100;

  const dispatch = createEventDispatcher();

  function startTimer(start_value) {
    let timer = setInterval(() => {
      isRunning = true;
      if (start_value > 0) {
        secondsLeft = secondsLeft - 1;
      } else if (start_value == 0) {
        secondsLeft = secondsLeft + 1;
      }

      if (secondsLeft == 0 || secondsLeft == totalSeconds) {
        clearInterval(timer);
        isRunning = false;
        dispatch("end", "END TIMER");
        //secondsLeft = totalSeconds;
      }
    }, 1000);
  }
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
  .start[disabled] {
    background-color: grey;
    cursor: not-allowed;
  }
</style>

<!-- <p class="">Timer</p> -->

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds Left : {secondsLeft}</h2>
</div>

<!-- <ProgressBar bp="offset-5@md 4@md 12@sm " progress={secondsLeft} /> -->

<!-- <div bp="grid">
  <div bp="offset-5@md 4@md 12@sm ">  -->
<ProgressBar progress={(secondsLeft / totalSeconds) * 100} />
<!--  </div>
</div> -->
<div bp="grid">
  <button
    disabled={isRunning}
    bp="offset-5@md 4@md 12@sm"
    class="start"
    on:click={() => {
      startTimer(secondsLeft);
    }}>Start</button>
</div>
