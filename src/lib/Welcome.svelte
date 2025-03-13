<script>
  import { Button } from "@sveltestrap/sveltestrap";

  export let role = 1;
  export let user = "User";
</script>

<div class="jumbotron">
  <h1 class="display-3">Hello, {user}}</h1>
  <p class="lead">
    This is a simple hero unit, a simple jumbotron-style component for calling
    extra attention to featured content or information.
  </p>
  <hr class="my-2" />
  <p>
    It uses utility classes for typography and spacing to space content out
    within the larger container.
  </p>

  {#if role == 3}
    <p class="lead">
      <Button color="primary">Learn Panel</Button>
    </p>
  {:else if role == 2}
    <p class="lead">
      <Button color="primary">Member Panel</Button>
    </p>
  {:else}
    <p class="lead">
      <Button color="primary">Public Panel</Button>
    </p>
  {/if}
</div>
