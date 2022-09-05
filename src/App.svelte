<script>
  import ContactCard from "./ContactCard.svelte";

  export let userName = "Diana";
  export let jobTitle = "Secrétaire médicale";
  export let description;
  export let imgLink =
    "https://2.bp.blogspot.com/-ZIRCrJuaVDY/U6A2tMp6i_I/AAAAAAAAIwk/DSMbTg5I0mI/s1600/Emoji.png";
  export let age;

  $: uppercaseName = userName.toUpperCase();
  $: console.log({ age });

  function incrementAge() {
    age++;
  }
</script>

<main>
  <p>Hello {uppercaseName}! You're {age}</p>
  <button on:click={incrementAge}>Increase Age</button>
  <input type="text" bind:value={userName} placeholder="userName" />
  <input type="text" bind:value={jobTitle} placeholder="job title" />
  <textarea rows="5" bind:value={description} placeholder="description" />
  <input type="text" bind:value={imgLink} placeholder="img link" />
</main>
<ContactCard {userName} {jobTitle} {description} {imgLink} />

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
