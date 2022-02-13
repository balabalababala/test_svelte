<script>
  let count = 0;

  $: doubled = count * 2;

  $: {
    console.log(`the count is ${count}`);
    //   alert(`I SAID THE COUNT IS ${count}`);
  }

  $: if (count >= 10) {
    //   alert(`count is dangerously high!`);
    console.log(`count is dangerously high!`);
    count = 9;
  }

  function handleClick() {
    // event handler code goes here
    count += 1;
  }

  // 数组的响应式
  let numbers = [1, 2, 3, 4];

  function addNumber() {
    numbers.push(numbers.length + 1);
    numbers = numbers; // 响应式，需要重新复制
  }

  $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<main>
  <h1>Reactive Test</h1>

  <button on:click={handleClick}>
    Clicked {count}
    {count === 1 ? "time" : "times"}
  </button>

  <p>{count} doubled is {doubled}</p>

  <p>{numbers.join(" + ")} = {sum}</p>

  <button on:click={addNumber}> Add a number </button>
</main>
