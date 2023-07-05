<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Header from "./lib/Header.svelte"
</script>


<Header />
<main>
  <div class="logo-box">
    <img src={svelteLogo} alt="Svelte Logo" class="logo">
  </div>

  <div class="title-box">
    <h2 class="title">Svelte Docs</h2>
    <h3 class="title-desc">SvelteDocs is a template for documentation.</h3>
  </div>

  <div class="button-box">
    <button class="button">
      Get Started
    </button>
  </div>

  <hr color="#2c3e50" class="border"/>

</main>

<style>
    main {
      width: 100vw;
    }

    .logo-box {
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .logo {
      width: 200px;
      margin-top: 50px;
    }

    .title-box {
      text-align: center;
    }

    .title {
      font-size: 2.75rem;
      font-weight: 500;
      margin-bottom: 0;
    }

    .title-desc {
      font-size: 1rem;
      opacity: 0.75;
    }

    .button-box {
      display: flex;
      justify-content: center;
      margin-top: 30px;
    }

    .button {
      background: #FF3E00;
      color: #fff;
      border: none;
      font-size: 1.1rem;
      padding: 18px;
      border-radius: 5px;
      font-weight: 700;
      letter-spacing: 0.8px;
      transition: 0.25s;
    }

    .button:hover {
      background: #ff6d3c;
    }

    .border {
      margin-top: 50px;
      opacity: 0.2;
    }
</style>
