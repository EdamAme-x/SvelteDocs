<script>
  // Lite <=> Dark
  import LiteMode from '../assets/sun.svg'
  
  function toTop() {
    location.href = "/";
  }

  if (!localStorage.getItem("_mode")) {
    localStorage.setItem("_mode", "Lite")
  }

  let _mode = localStorage.getItem("_mode");

  if (_mode == "Lite") {
    // Lite view
  }else {
    // Dark view
  }

</script>

<header>
  <h1 on:click={toTop}>Svelte Docs</h1>
  <nav>
  <img src={LiteMode} alt="LiteIcon" height="30" class="icon">
    <a href="/ref">
      Reference
    </a>
    <a href="https://github.com/EdamAme-x/SvelteDocs">
      GitHub
    </a>
  </nav>
</header>
<hr color="#2c3e50"/>

<style>
h1 {
  margin: 0;
  padding: 10px 18px 0px 10px;
  font-size: 1.25rem;
  font-weight: 600;
  opacity: 0.95;
}

header {
  width: 100vw;
  height: auto;
  display: flex;
}

hr {
  height: 0.3px;
  opacity: 0.15;
}

nav {
  display: flex;
  margin-right: 25px;
  margin-left: auto;
}

nav a {
  color: inherit;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  padding: 14px 8px 0px 8px;
}

.icon {
  margin-top: 8px;
  margin-right: 3px;
}
</style>