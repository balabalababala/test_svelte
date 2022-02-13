<script>
  import Nested from './Nested.svelte';
  import PropsTest from './Props.test.svelte';
  import ReactiveTest from './Reactive.test.svelte';
  export let name;
  let name2 = "abc"
</script>

<main>
  <h1>Hello {name}!</h1>
  <h1>Hello {name2}!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
  <Nested answer={name2}/>
  <PropsTest answer={"Props Test"} arr={[1,2,3]} />
  <ReactiveTest />
  <div>asfas</div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
