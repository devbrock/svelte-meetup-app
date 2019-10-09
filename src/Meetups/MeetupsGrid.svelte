<script>
  import MeetupItem from "./MeetupItem.svelte";
  export let meetups;

  function getDetails(event) {
    console.log(event.detail);
  }
</script>

<div class="row">
  {#each meetups as meetup}
    <div class="col-md-6 col-sm-12">
      <MeetupItem
        title={meetup.title}
        subtitle={meetup.subtitle}
        description={meetup.description}
        imageUrl={meetup.imageUrl}
        address={meetup.address}
        email={meetup.contactEmail}
        on:show-details={getDetails} />
    </div>
  {/each}
</div>
