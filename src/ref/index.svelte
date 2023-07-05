<script>
  import svelteLogo from '../assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Header from "../lib/Header.svelte"
  import Footer from "../lib/Footer.svelte"

  import SideSvg from "../assets/side.svg"

  import Docs from "./docs.svelte"
</script>


<Header />
<main>
  <div class="side-box">
    <img src={SideSvg} class="side" alt="side-svg" width="30">
  </div>

  <div class="docs-main">
    <Docs />
  </div>
</main>
<Footer />

<style>
    main {
      width: 100vw;
    }

    .side-box {
      width: 40px;
      height: 40px;
      padding: 5px;
      border-radius: 10px;
      position: fixed;
      top: 60px;
      left: 15px;
      backdrop-filter: invert(80%);
    }

    .docs-main {
      margin-top: 50px;
      text-align: center;
    }
</style>
