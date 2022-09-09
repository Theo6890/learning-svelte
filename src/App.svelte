<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./MeetUps/MeetupGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";

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
    <TextInput
      id="title"
      label="title"
      value={title}
      on:input={(event) => (title = event.target.value)}
    />

    <TextInput
      id="subtitle"
      label="subtitle"
      value={subtitle}
      on:input={(event) => (subtitle = event.target.value)}
    />

    <TextInput
      id="address"
      label="address"
      value={address}
      on:input={(event) => (address = event.target.value)}
    />

    <TextInput
      id="url"
      label="url"
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
    />

    <TextInput
      id="email"
      label="email"
      value={email}
      type="email"
      on:input={(event) => (email = event.target.value)}
    />

    <TextInput
      id="description"
      label="description"
      controlType="textarea"
      rows="3"
      value={description}
      on:input={(event) => (description = event.target.value)}
    />

    <button type="submit">Save</button>
  </form>

  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
  }

  form {
    widows: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>
