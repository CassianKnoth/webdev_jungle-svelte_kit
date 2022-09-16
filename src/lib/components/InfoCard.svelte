<script lang="ts">
  import Link from "./Link.svelte";

  export let headline: string = "Info";
  export let text: string = "Lorem ipsum";
  export let imgURL: string = "/";

  export let linkData = {
    destination: "/",
    title: "",
    alt: "link",
  };
</script>

<div class="card" style="--imgURL: url({imgURL})">
  <div class="info">
    <div>
      <h3>{headline}</h3>
      <hr />
      <p>
        <!-- careful with @html -->
        {@html text}
      </p>
    </div>
    <div class="neutralizeFlex">
      <Link {...linkData} />
    </div>
  </div>
</div>

<style>
  .card {
    width: 100%;
    height: 40vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    border-radius: 0.5rem;
    box-shadow: 0 0.2rem 2rem rgba(0, 0, 0, 0.1);
    overflow: hidden;
    background-size: 100%;
    transition: transform 0.2s ease;
    background-image: var(--imgURL);
  }

  @media only screen and (min-width: 600px) {
    .card {
      height: 60vh;
    }
  }

  /* info */

  .card .info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 70%;
    background-color: var(--color-neutral);
    padding: calc(var(--gap) / 2);
    transition: height 0.2s ease-out;
  }

  .card .info div > *:not(:last-child) {
    margin-bottom: 1rem;
  }

  .card .info hr {
    border-top: 1px solid var(--color-dark);
  }

  /* hover */

  .card:hover {
    transform: scale(1.05);
  }

  .card .info div > *:not(:last-child) {
    transition: margin-bottom 0.2s ease-out;
  }

  .card:hover .info div > *:not(:last-child) {
    margin-bottom: 1.5rem;
  }

  .card:hover .info {
    height: 80%;
  }
</style>
