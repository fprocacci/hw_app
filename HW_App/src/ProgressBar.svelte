<script>
  // passing a prop to the Progress Bar
  export let progress = 100;
</script>

<style>
  .progress-container {
    margin: 20px 0;
    border: 2px solid orange;
    /* width: 50%;*/
  }
  .progress-bar {
    height: 30px;
    background-color: red;
  }
</style>

<!-- style="width: 100%;-->
<div bp="grid">
  <div class="progress-container" bp="offset-5@md 4@md 12@sm ">
    <div class="progress-bar" style="width:{progress}%;">
      <span class="sr-only">%{progress}</span>
    </div>
  </div>
</div>
