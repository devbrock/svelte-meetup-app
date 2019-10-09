<script>
  import Header from "./UI/Header.svelte";
  import MeetupsGrid from "./Meetups/MeetupsGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";

  let meetups = [
    {
      id: "m1",
      title: "Svelte Bootcamp",
      subtitle: "Learn Svelte in One Day",
      description: "In this meetup, we will learn Svelte.",
      imageUrl: "https://bit.ly/31UinLz",
      address: "100 Orange Drive, Chicago, IL",
      contactEmail: "instructor@email.com"
    },
    {
      id: "m2",
      title: "React Bootcamp 2",
      subtitle: "Learn React in One Day",
      description: "In this meetup, we will learn React.",
      imageUrl: "https://bit.ly/2IzCBCS",
      address: "100 Blue Drive, Baltimore, MY",
      contactEmail: "instructor2@email.com"
    },
    {
      id: "m3",
      title: "Angular Bootcamp 3",
      subtitle: "Learn Angular in One Day",
      description: "In this meetup, we will learn Angular.",
      imageUrl: "https://bit.ly/320RKVh",
      address: "100 Red Street, New York, NY",
      contactEmail: "instructor3@email.com"
    }
  ];

  let title = "";
  let subtitle = "";
  let description = "";
  let email = "";
  let imageUrl = "";
  let address = "";
  let contactEmail = "";

  function addMeetup() {
    let newMeetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      imageUrl: imageUrl,
      address: address,
      contactEmail: email
    };

    meetups = [newMeetup, ...meetups];
  }
</script>

<style>

</style>

<Header />
<div class="container my-4">
  <form on:submit|preventDefault={addMeetup}>

    <TextInput
      id="title"
      label="Title"
      value={title}
      controlType="text"
      type="text"
      on:input={event => (title = event.target.value)} />
    <TextInput
      id="subtitle"
      label="Subtitle"
      value={subtitle}
      controlType="text"
      type="text"
      on:input={event => (subtitle = event.target.value)} />
    <TextInput
      id="imageUrl"
      label="Link to Image"
      value={imageUrl}
      type="text"
      controlType="text"
      on:input={event => (imageUrl = event.target.value)} />
    <TextInput
      id="description"
      label="Description"
      value={description}
      controlType="textarea"
      rows="3"
      type="text"
      on:input={event => (description = event.target.value)} />
    <TextInput
      id="address"
      label="Address"
      value={address}
      controlType="text"
      type="address"
      on:input={event => (address = event.target.value)} />
    <TextInput
      id="contactEmail"
      label="Contact Email"
      value={contactEmail}
      controlType="text"
      type="email"
      on:input={event => (contactEmail = event.target.value)} />

    <Button
      type="submit"
      background="primary"
      textcolor="light"
      caption="Add Meetup" />
  </form>

  <MeetupsGrid {meetups} />

</div>
