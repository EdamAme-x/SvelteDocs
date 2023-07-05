<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Header from "./lib/Header.svelte"
  import Footer from "./lib/Footer.svelte"

  function toRef() {
    location.href = "/#/ref"
  }
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
    <button class="button" on:click={toRef}>
      Get Started
    </button>
  </div>

  <hr color="#2c3e50" class="border"/>

  <div class="feature-box">
    <div class="feature">
      <h3>In Svelte.</h3>
      <div class="feature-text">
        Template for creating a documentation site using Svelte, complete with Svelte.
      </div>
    </div>

    <div class="feature">
      <h3>Easy &amp; Fast</h3>
      <div class="feature-text">
        It can be built quickly because it is already a complete Template.
        It also has the ease of Svelte.
      </div>
    </div>

    <div class="feature">
      <h3>Customize</h3>
      <div class="feature-text">
        Because it is written in native Svelte and CSS, it is highly customizable.
      </div>
    </div>
  </div>

  <hr color="#2c3e50" class="border"/>

</main>
<Footer />

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

    .feature {
      width: 33%;
    }

    @media (max-width: 800px) {
      .feature {
        width: 100%;
      }
    }

    .feature h3 {
      font-size: 1.55rem;
      margin: 5px;
      margin-bottom: 10px;
      text-align: left;
      padding-left: 12px;
      font-weight: 500;
    }

    .feature-text {
      font-size: 1.1rem;
      opacity: 0.8;
      margin-left: 10px;
      line-height: 1.41;
    }

    .feature-box {
      display: flex;
      flex-wrap: wrap;
      margin: 10px;
      margin-top: 25px;
      margin-bottom: 40px;
    }
</style>
