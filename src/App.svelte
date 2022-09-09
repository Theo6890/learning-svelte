<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./MeetUps/MeetupGrid.svelte";

  const meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours",
      description:
        "In this meetup, we will have some meetin to learn about code",
      imageUrl:
        "https://static.vecteezy.com/system/resources/previews/000/423/133/original/vector-code-optimization-icon.jpg",
      address: "27th Nerd Road, 42352 New York",
      contactEmail: "code@test.com",
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Lets go for swimming",
      description: "We will swim some rounds!",
      imageUrl:
        "https://static.vecteezy.com/system/resources/previews/000/571/419/original/vector-network-icon.jpg",
      addres: "Swiming Pool of Town, Water Road, London SE3SZ5",
      contactEmail: "swim@test.com",
    },
  ];
</script>

<Header />

<main>
  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
  }
</style>
