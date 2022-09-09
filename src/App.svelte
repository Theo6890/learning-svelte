<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./MeetUps/MeetupGrid.svelte";

  let title = "",
    subtitle = "",
    address = "",
    description = "",
    imageUrl = "",
    email = "";

  let meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours",
      address: "27th Nerd Road, 42352 New York",
      description:
        "In this meetup, we will have some meetin to learn about code",
      imageUrl:
        "https://static.vecteezy.com/system/resources/previews/000/423/133/original/vector-code-optimization-icon.jpg",
      contactEmail: "code@test.com",
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Lets go for swimming",
      addres: "Swiming Pool of Town, Water Road, London SE3SZ5",
      description: "We will swim some rounds!",
      imageUrl:
        "https://static.vecteezy.com/system/resources/previews/000/571/419/original/vector-network-icon.jpg",
      contactEmail: "swim@test.com",
    },
  ];
  function addMeetup() {
    const newMeetup = {
      id: Math.random(),
      title,
      subtitle,
      address,
      description,
      imageUrl,
      contactEmail: email,
    };

    meetups = [newMeetup, ...meetups];
  }
</script>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <div class="form-control">
      <label for="title">Title</label>
      <input
        type="text"
        id="title"
        placeholder="set title"
        bind:value={title}
      />

      <label for="subtitle">Sub-Title</label>
      <input
        type="text"
        id="subtitle"
        placeholder="set subtitle"
        bind:value={subtitle}
      />

      <label for="address">Address</label>
      <input
        type="text"
        id="address"
        placeholder="set address"
        bind:value={address}
      />

      <label for="url">Image Url</label>
      <input
        type="text"
        id="url"
        placeholder="set url of your image"
        bind:value={imageUrl}
      />

      <label for="email">Email</label>
      <input
        type="email"
        id="email"
        placeholder="set email"
        bind:value={email}
      />
    </div>
    <div class="form-control">
      <label for="description">Description</label>
      <textarea
        rows="3"
        id="description"
        placeholder="set description"
        bind:value={description}
      />
    </div>

    <button type="submit">Save</button>
  </form>

  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
  }
</style>
