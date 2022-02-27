<script>
  export let progess = 0;
</script>

<style>
  .progess-container {
    width: 100%;
    height: 30px;
    border: 3px solid black;
    margin: 1rem 0;
    font-weight: 600;
    font-size: 1.4rem;
    position: relative;
  }
  .progess-bar {
    height: 100%;
    background-color: green;
  }
  .sr-only {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>

<div class='progess-container'>
<div class='progess-bar' style='width: {progess}%'>
<span class='sr-only'>%{progess.toFixed(2)}</span>
</div>
</div>