<!--Display all event from http://127.0.0.1:8000/api/events with fetch-->
<script>
  import { onMount } from 'svelte';
  
  let events = [];
  onMount(async () => {
    const res = await fetch('http://127.0.0.1:8000/api/events');
    events = await res.json();
  });
</script>

<h1>Events</h1>
<!-- Display event as cards-->
{#each events.member as event}
  <div>
    <h2>{event.name}</h2>
    <p>{event.date}</p>
  </div>
{/each}
<!-- Add the possibility-->