<script>
  const puzzles = [
    {
      title: "The Look",
      author: "Sara Teasdale",
      inProgress: false,
      difficulty: 1,
    },
    {
      title: "The Sunday News",
      author: "Dana Gioia",
      inProgress: true,
      difficulty: 2,
    },
    {
      title: "Because I Could Not Stop For Death",
      author: "Emily Dickinson",
      inProgress: false,
      difficulty: 3,
    },
  ];
</script>

<div class="container">
  <header class="header">
    <button class="button">
      <span>Filters</span>
      <img class="icon" src="/images/category.svg" alt="category-icon" />
    </button>

    <button class="button">
      <span>Settings</span>
      <img class="icon" src="/images/settings.svg" alt="settings-icon" />
    </button>

    <button class="button">
      <span>Info</span>
      <img class="icon" src="/images/info.svg" alt="info-icon" />
    </button>
  </header>

  <div class="section">
    <div class="heading">LATEST</div>
    {@render link(puzzles[0])}
  </div>

  <div class="section section--archive">
    <div class="heading">ARCHIVE</div>
    {#each puzzles.slice(1) as puzzle}
      {@render link(puzzle)}
    {/each}
  </div>
</div>

{#snippet link(puzzle)}
  <div class="puzzle">
    <div class="inner">
      <div class="meta">
        <div class="progress">
          <span>{puzzle.inProgress ? "In-Progress" : "Start"}</span>
          <div class="state">
            <div class="half" style:display={puzzle.inProgress ? "block" : "none"}></div>
          </div>
        </div>
        <div class="difficulty">
          <span>Difficulty:</span>
          <div class="meter meter-{puzzle.difficulty}">
            {#each { length: puzzle.difficulty }}
              <div class="box"></div>
            {/each}
            {#each { length: 4 - puzzle.difficulty }}
              <div class="box box-filled"></div>
            {/each}
          </div>
        </div>
      </div>

      <h2 class="title">{puzzle.title}</h2>
      <h3 class="author">By {puzzle.author}</h3>
    </div>
  </div>
{/snippet}

<style>
  .container {
    margin: 0 auto;
    max-width: 500px;
  }

  .header {
    margin-bottom: 48px;
    display: flex;
    gap: 16px;
    padding: 8px;
    border: 1.5px solid #4d4d4d;
    justify-content: space-around;
  }

  .button {
    background: none;
    padding: 0;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 4px;
    font-weight: 500;
    font-family: "DM Mono", monospace;
    font-size: 12px;
    padding: 4px 8px;
    border-radius: 5px;
    text-transform: uppercase;
  }

  .button:hover {
    background: #ddd;
  }

  .icon {
    filter: brightness(0) saturate(100%);
    width: 20px;
  }

  .section--archive {
    margin-top: 48px;
  }

  .heading {
    text-transform: uppercase;
    border-bottom: 1.5px solid #4d4d4d;
    padding-bottom: 4px;
  }

  /* style SNIPPET */
  .puzzle {
    cursor: pointer;
  }

  .puzzle:hover {
    background: #eee;
  }

  .inner {
    padding: 16px 0;
    border-bottom: 1px solid #cccccc;
    margin-left: 12px;
  }

  .meta {
    font-size: 13px;
    display: flex;
    gap: 16px;
  }

  .difficulty,
  .progress {
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .state {
    border: 1px solid black;
    border-radius: 50%;
    width: 10px;
    height: 10px;
    margin-top: -1px;
    position: relative;
    overflow: hidden;
  }

  .half {
    position: absolute;
    right: 0;
    width: 5px;
    height: 10px;
    background: black;
  }

  .meter {
    margin-top: -1px;
    display: flex;
  }

  .meter-1 {
    background: #2fe6b2;
  }

  .meter-2 {
    background: #ffd52d;
  }

  .meter-3 {
    background: #ff743d;
  }

  .meter-4 {
    background: #ff0000;
  }

  .box {
    border: 1px solid black;
    border-right: none;
    width: 10px;
    height: 10px;
  }

  .box-filled {
    background: white;
  }

  .box:last-child {
    border-right: 1px solid black;
  }

  .title {
    margin: 0;
    padding: 0;
    font-size: 28px;
    font-family: "Mazius", serif;
    font-weight: 400;
    line-height: 100%;
    margin-top: 8px;
  }

  .author {
    margin: 0;
    margin-top: 4px;
    padding: 0;
    text-transform: uppercase;
    font-weight: 400;
    opacity: 0.7;
    font-size: 13px;
  }
</style>
