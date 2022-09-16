<script lang="ts">
  import InfoCard from "../InfoCard.svelte";
  import Slide from "./Slide.svelte";

  const infoCardData = [
    {
      headline: "HTML",
      text: `The <span class="bold">H</span>yper<span class="bold">t</span>ext <span class="bold">M</span>arkup <span class="bold">L</span>anguage allows you to build the architecture of your web application.`,
      imgURL: "img/teaser/html-teaser.jpg",
      linkData: {
        destination: "https://www.w3schools.com/html/default.asp",
        title: "Learn HTML",
        alt: "Link to w3schools HTML tutorial",
        target: "_blank",
      },
    },
    {
      headline: "CSS",
      text: `With <span class="bold">C</span>ascading <span class="bold">S</span>tyle <span class="bold">S</span>eets you can control the appearance of your web application.`,
      imgURL: "img/teaser/css-teaser.jpg",
      linkData: {
        destination: "https://www.w3schools.com/css/default.asp",
        title: "Learn CSS",
        alt: "Link to w3schools CSS tutorial",
        target: "_blank",
      },
    },
    {
      headline: "JavaScript",
      text: `<span class="bold">J</span>ava<span class="bold">S</span>cript truly brings your web application to life and allows for deep interactivity.`,
      imgURL: "img/teaser/js-teaser.jpg",
      linkData: {
        destination: "https://www.w3schools.com/js/default.asp",
        title: "Learn JavaScript",
        alt: "Link to w3schools JavaScript tutorial",
        target: "_blank",
      },
    },
  ];
</script>

<Slide>
  <h1>Here are some resources for your expedition:</h1>
  <div class="tricolon">
    {#each infoCardData as infoCardItem}
      <InfoCard {...infoCardItem} />
    {/each}
  </div>
</Slide>

<style>
  h1 {
    text-align: center;
  }

  .tricolon {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: var(--gap);
  }

  @media only screen and (min-width: 600px) {
    .tricolon {
      flex-direction: row;
      flex-wrap: wrap;
    }

    .tricolon :global(.card) {
      flex-basis: calc(50% - var(--gap) / 2);
    }
  }

  @media only screen and (min-width: 1200px) {
    .tricolon :global(.card) {
      flex: 1;
    }
  }
</style>
