<script>
  import Progess from "./Progess.svelte";
  const totalSeconds = 20;
  let secondsLeft = totalSeconds;
  let isRunning = false;

  $: progess = ((totalSeconds - secondsLeft) / totalSeconds) * 100;

  function startTimer() {
    isRunning = true;
    const timer = setInterval(() => {
      secondsLeft -= 1;
      if (secondsLeft === 0) {
        clearInterval(timer);
        isRunning = false;
        secondsLeft = totalSeconds;
      }
    }, 1000);
  }
</script>

<style>
  button {
    background-color: #222;
    color: #fff;
    width: 100%;
    padding: 0.6rem;
    margin-bottom: 2rem;
    border-color: #222;
    cursor: pointer;
    transition: 0.3s all ease;
  }
  button:hover {
    background-color: #fff;
    color: #222;
  }
  button[disabled] {
    background-color: grey;
    border: none;
  }
</style>

Time left: {secondsLeft}
<Progess {progess} />
<button on:click={startTimer} disabled={isRunning}>
  Start
</button>