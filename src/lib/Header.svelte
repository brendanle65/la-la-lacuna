<script>
</script>

<header>
  <span class="segment">
    <span class="title title--la">La</span>
    <span class="dot"></span>
  </span>
  <span class="segment segment--middle">
    <span class="title title--la">La</span>
    <span class="dot"></span>
  </span>
  <span class="segment">
    <span class="title title--lacuna">Lacuna</span>
    <span class="subtitle">a fill-in-the-<span class="underline">blank</span> poetry game</span>
  </span>
</header>

<style>
  header {
    width: max-content;
    margin: 0 auto;
  }

  .segment {
    position: relative;
  }

  .segment--middle {
    margin: 0 6px;
  }

  .title {
    font-family: "DM Mono", monospace;
    font-weight: 500;
    font-style: italic;
  }

  .title--la {
    font-size: 32px;
  }

  .title--lacuna {
    text-transform: uppercase;
    font-size: 48px;
  }

  .dot {
    width: 6px;
    height: 6px;
    background: black;
    border-radius: 50%;
    position: absolute;
    left: calc(50% - 1px);
    transform: translateX(-100%);
    bottom: -9px;
  }

  .subtitle {
    font-family: "Courier Prime", monospace;
    font-size: 11px;
    position: absolute;
    transform: translateY(100%);
    bottom: -1px;
    left: 0;
    text-indent: -1em;
    padding-left: 1em;
    margin-left: 16px;
  }

  .underline {
    text-decoration: underline;
  }

  @media screen and (min-width: 720px) {
    .segment--middle {
      margin: 0 12px;
    }

    .title--la {
      font-size: 48px;
    }

    .title--lacuna {
      font-size: 72px;
    }
  }
</style>
