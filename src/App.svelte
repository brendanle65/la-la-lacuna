<script>
  import Header from "./lib/Header.svelte";
  import Footer from "./lib/Footer.svelte";
  import Index from "./views/Index.svelte";
</script>

<div class="container">
  <Header></Header>
  <main class="main">
    <Index></Index>
  </main>
  <Footer></Footer>
</div>

<style>
  .container {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    padding: 16px;
    box-sizing: border-box;
  }

  .main {
    margin-top: 64px;
    margin-bottom: 32px;
  }

  @media screen and (min-width: 720px) {
    .container {
      padding: 24px 32px;
    }
  }
</style>
