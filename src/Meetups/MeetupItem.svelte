<script>
  import Button from "../UI/Button.svelte";
  import { createEventDispatcher } from "svelte";

  export let title;
  export let subtitle;
  export let imageUrl;
  export let description;
  export let address;
  export let email;

  let favBackground = "warning";
  let favTextcolor = "dark";
  let favCaption = "Favorite";

  const dispatch = createEventDispatcher();

  function favoriteMeetup() {
    favBackground = "dark";
    favTextcolor = "warning";
    favCaption = "Favorited";
  }

  function showDetails() {
    dispatch("show-details", { id: "m1" });
  }
</script>

<div class="card text-dark bg-light my-4 p-4 shadow-lg">
  <img src={imageUrl} alt={title} class="card-img-top rounded mb-2" />
  <header>
    <h1 class="card-title">{title}</h1>
    <h2 class="card-title">{subtitle}</h2>
  </header>
  <p class="card-text">{description}</p>
  <h6>{address}</h6>
  <footer>
    <Button
      caption="Show Details"
      background="primary"
      textcolor="light"
      on:click={showDetails} />
    <Button
      caption="Get in touch"
      href="mailto:{email}"
      background="info"
      textcolor="light" />
    <Button
      caption={favCaption}
      background={favBackground}
      textcolor={favTextcolor}
      on:click={favoriteMeetup} />
  </footer>
</div>
