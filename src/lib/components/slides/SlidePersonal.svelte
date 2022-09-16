<script lang="ts">
  import Link from "../Link.svelte";
  import Slide from "./Slide.svelte";

  const linkData = {
    destination: "/ESJ-blog",
    title: "Eloquent JavaScript Blog",
    alt: "link to Eloquent JavaScript blog",
  };
</script>

<Slide>
  <div class="wrapper">
    <div class="hero">
      <img src="/img/hero.jpg" alt="Portrait of me – Cassian" />
    </div>
    <div class="welcome">
      <h1>My name is Cassian</h1>
      <h2>Maybe I can guide you a little bit...</h2>
      <p>
        On this site you can find some useful links which provide you with
        valuable and hands on resources for getting started with web
        development.
      </p>
      <p>Check out my current adventure here:</p>
      <Link {...linkData} />
    </div>
  </div>
</Slide>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
    text-align: center;
  }

  .hero img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 0.5rem;
    margin-bottom: 1rem;
    box-shadow: 0 0.2rem 2rem rgba(0, 0, 0, 0.2);
  }

  @media only screen and (min-width: 768px) {
    .wrapper {
      flex-direction: row;
      text-align: left;
      gap: var(--gap);
    }

    .hero {
      flex: 1;
    }

    .welcome {
      flex: 2;
    }

    h1 {
      text-align: left;
    }
  }

  .welcome > *:not(:last-child) {
    margin-bottom: 1rem;
  }
</style>
