<script>
  import Button from "../UI/Button.svelte";

  export let title;
  export let subtitle;
  export let imageUrl;
  export let description;
  export let address;
  export let email;
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
    <Button caption="Show Details" background="primary" textcolor="light" />
    <Button
      caption="Get in touch"
      href="mailto:{email}"
      background="info"
      textcolor="light" />
    <Button caption="Favorite" background="warning" textcolor="dark" />
  </footer>
</div>
