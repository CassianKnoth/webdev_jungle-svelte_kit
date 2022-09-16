<script lang="ts">
</script>

<a href="#next" class="scrollDownIndicator" alt="">
  <div class="arrow">&#10095;</div>
  <div class="arrow">&#10095;</div>
  <div class="arrow">&#10095;</div>
</a>

<style>
  .scrollDownIndicator {
    color: var(--color-neutral);
    font-size: 2rem;
    transform: rotate(90deg);
    margin-top: 2rem;
    text-shadow: none;
    position: relative;
  }

  .scrollDownIndicator .arrow {
    animation: 2s ease-out infinite;
    opacity: 1;
    transform: translateX(0);
    line-height: 0;
    position: absolute;
  }

  .scrollDownIndicator .arrow:nth-child(1) {
    animation-name: moveOut;
  }

  @keyframes moveOut {
    0% {
      opacity: 1;
      transform: translateX(0);
    }
    50% {
      /* movement */
      opacity: 0;
      transform: translateX(40px);
    }
    75% {
      opacity: 0;
      transform: translateX(40px);
    }
    76% {
      /* invisible, back to original position */
      opacity: 0;
      transform: translateX(0);
    }
    77% {
      /* back at original position and orginal opacity – loop complete */
      opacity: 1;
      transform: translateX(0);
    }
    100% {
      opacity: 1;
      transform: translateX(0);
    }
  }

  .scrollDownIndicator .arrow:nth-child(2) {
    animation-name: moveDown;
  }

  @keyframes moveDown {
    0% {
      opacity: 0.5;
      transform: translateX(-10px);
    }
    50% {
      /* movement */
      opacity: 1;
      transform: translateX(0);
    }
    77% {
      opacity: 1;
      transform: translateX(0);
    }
    78% {
      /* invisible after .arrow:nth-child(1) is back at this position and fully visible */
      opacity: 0;
      transform: translateX(0);
    }
    80% {
      /* invisible, back to original position */
      opacity: 0;
      transform: translateX(-10px);
    }
    81% {
      /* back at original position and orginal opacity – loop complete */
      opacity: 0.5;
      transform: translateX(-10px);
    }
    100% {
      opacity: 0.5;
      transform: translateX(-10px);
    }
  }

  .scrollDownIndicator .arrow:nth-child(3) {
    animation-name: moveIn;
  }

  @keyframes moveIn {
    0% {
      opacity: 0;
      transform: translateX(-30px);
    }
    50% {
      /* movement */
      opacity: 0.5;
      transform: translateX(-10px);
    }
    80% {
      opacity: 0.5;
      transform: translateX(-10px);
    }
    81% {
      opacity: 0;
      transform: translateX(-10px);
    }
    82% {
      opacity: 0;
      transform: translateX(-30px);
    }
    100% {
      opacity: 0;
      transform: translateX(-30px);
    }
  }
</style>
